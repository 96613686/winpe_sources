# BasepCreateProcessParameters

- ea: `0x1800ef8f0`
- end: `0x1800efe7a`
- name: `BasepCreateProcessParameters`
- size: `1418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18008e220`

## callees

- `0x18004b9d0`
- `0x1800ef8f0`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800efc22`
- `ntdll!RtlInitUnicodeString` at `0x1800efc22`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef983`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef9a1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef9c6`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef9e3`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800efa17`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800efa35`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800efa72`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef983`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef9a1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef9c6`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800ef9e3`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800efa17`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800efa35`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800efa72`
- `ntdll!RtlFreeHeap` at `0x1800efde1`
- `ntdll!RtlFreeHeap` at `0x1800efde1`
- `ntdll!RtlDestroyProcessParameters` at `0x1800efe69`
- `ntdll!RtlDestroyProcessParameters` at `0x1800efe69`
- `ntdll!LdrGetDllDirectory` at `0x1800efc06`
- `ntdll!LdrGetDllDirectory` at `0x1800efd9f`
- `ntdll!LdrGetDllDirectory` at `0x1800efc06`
- `ntdll!LdrGetDllDirectory` at `0x1800efd9f`
- `ntdll!RtlCreateProcessParametersWithTemplate` at `0x1800efa98`
- `ntdll!RtlCreateProcessParametersWithTemplate` at `0x1800efa98`
- `ntdll!RtlAllocateHeap` at `0x1800efd7e`
- `ntdll!RtlAllocateHeap` at `0x1800efd7e`

## pseudocode

```c
PRTL_USER_PROCESS_PARAMETERS __fastcall BasepCreateProcessParameters(
        const WCHAR *a1,
        __int128 *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const WCHAR *a5,
        const WCHAR *a6,
        char a7,
        __int64 a8,
        __int64 a9,
        int a10,
        int a11,
        int a12,
        __int64 a13,
        __int64 a14)
{
  struct _PEB *v17; // r15
  __int128 v18; // xmm0
  NTSTATUS inited; // ebx
  char v20; // si
  const WCHAR *v21; // rdx
  int DllDirectory; // eax
  struct _RTL_USER_PROCESS_PARAMETERS *v24; // rcx
  struct _RTL_USER_PROCESS_PARAMETERS *v25; // rcx
  PRTL_USER_PROCESS_PARAMETERS ProcessParameters; // [rsp+20h] [rbp-E0h] BYREF
  PCWSTR SourceString; // [rsp+28h] [rbp-D8h]
  PCWSTR v28; // [rsp+30h] [rbp-D0h]
  _BYTE v29[56]; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v30; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v31; // [rsp+90h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING v35; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING v36; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v37; // [rsp+110h] [rbp+10h] BYREF
  __int16 v38; // [rsp+120h] [rbp+20h]
  __int16 v39; // [rsp+122h] [rbp+22h]
  __int64 v40; // [rsp+128h] [rbp+28h]
  struct _UNICODE_STRING v41; // [rsp+450h] [rbp+350h] BYREF

  v28 = a1;
  SourceString = a6;
  ProcessParameters = 0;
  memset_0(v29, 0, 0x448u);
  v17 = NtCurrentPeb();
  v18 = *a2;
  v34 = a8;
  v32 = v18;
  inited = RtlInitUnicodeStringEx(&DestinationString, a4);
  if ( inited < 0 )
    goto LABEL_26;
  inited = RtlInitUnicodeStringEx(&v30, a3);
  if ( inited < 0 )
    goto LABEL_26;
  inited = RtlInitUnicodeStringEx(&v41, SourceString);
  if ( inited < 0 )
    goto LABEL_26;
  inited = RtlInitUnicodeStringEx(&v31, a5);
  if ( inited < 0 )
    goto LABEL_26;
  v20 = 0;
  if ( a5 || a7 || (a12 & 0x10000) != 0 )
    goto LABEL_6;
  DllDirectory = LdrGetDllDirectory(&v31);
  if ( v31.Length <= 2u || DllDirectory != -1073741789 )
  {
    RtlInitUnicodeString(&v31, 0);
    goto LABEL_6;
  }
  v31.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v31.Length);
  if ( !v31.Buffer )
  {
    inited = -1073741801;
    goto LABEL_26;
  }
  v31.MaximumLength = v31.Length;
  inited = LdrGetDllDirectory(&v31);
  if ( inited >= 0 )
  {
    v20 = 1;
LABEL_6:
    inited = RtlInitUnicodeStringEx(&v36, *(PCWSTR *)(a9 + 16));
    if ( inited >= 0 )
    {
      inited = RtlInitUnicodeStringEx(&v37, *(PCWSTR *)(a9 + 8));
      if ( inited >= 0 )
      {
        v21 = *(const WCHAR **)(a9 + 24);
        v40 = *(_QWORD *)(a9 + 72);
        v38 = *(_WORD *)(a9 + 66);
        v39 = v38;
        if ( !v21 )
          v21 = v28;
        inited = RtlInitUnicodeStringEx(&v35, v21);
        if ( inited >= 0 )
        {
          inited = RtlCreateProcessParametersWithTemplate(&ProcessParameters, v29, 1);
          if ( inited >= 0 )
          {
            ProcessParameters->StartingX = *(_DWORD *)(a9 + 32);
            ProcessParameters->StartingY = *(_DWORD *)(a9 + 36);
            ProcessParameters->CountX = *(_DWORD *)(a9 + 40);
            ProcessParameters->CountY = *(_DWORD *)(a9 + 44);
            ProcessParameters->CountCharsX = *(_DWORD *)(a9 + 48);
            ProcessParameters->CountCharsY = *(_DWORD *)(a9 + 52);
            ProcessParameters->FillAttribute = *(_DWORD *)(a9 + 56);
            ProcessParameters->WindowFlags = *(_DWORD *)(a9 + 60);
            ProcessParameters->ShowWindowFlags = *(unsigned __int16 *)(a9 + 64);
            if ( (a10 & 0x200) != 0 )
              ProcessParameters[1].Flags = 0;
            else
              ProcessParameters[1].Flags = v17->ProcessParameters[1].Flags;
            if ( (*(_DWORD *)(a9 + 60) & 0x700) != 0 )
            {
              if ( a14 || (*(_DWORD *)(a9 + 60) & 0x100) == 0 || (a12 & 4) != 0 )
              {
                ProcessParameters->StandardInput = *(HANDLE *)(a9 + 80);
                ProcessParameters->StandardOutput = *(HANDLE *)(a9 + 88);
                ProcessParameters->StandardError = *(HANDLE *)(a9 + 96);
              }
              else
              {
                ProcessParameters->StandardInput = 0;
                ProcessParameters->StandardOutput = 0;
                ProcessParameters->StandardError = 0;
              }
            }
            if ( (a10 & 8) != 0 )
            {
              ProcessParameters->ConsoleHandle = (HANDLE)-1LL;
            }
            else if ( (a10 & 0x10) != 0 )
            {
              ProcessParameters->ConsoleHandle = (HANDLE)-2LL;
            }
            else if ( (a10 & 0x8000000) != 0 )
            {
              ProcessParameters->ConsoleHandle = (HANDLE)-3LL;
            }
            else
            {
              if ( a13 && *(_QWORD *)a13 )
              {
                ProcessParameters->ConsoleHandle = **(HANDLE **)a13;
                ProcessParameters->ConsoleFlags |= 2u;
                if ( *(_BYTE *)(a13 + 8) )
                  ProcessParameters->ConsoleFlags |= 4u;
              }
              else
              {
                ProcessParameters->ConsoleHandle = (HANDLE)xmmword_1803AB0B0;
                if ( !ProcessParameters->ConsoleHandle )
                  ProcessParameters->ConsoleHandle = v17->ProcessParameters->ConsoleHandle;
              }
              if ( (*(_DWORD *)(a9 + 60) & 0x700) == 0 && a11 )
              {
                v24 = v17->ProcessParameters;
                if ( (v24->WindowFlags & 0x200) == 0 )
                  ProcessParameters->StandardInput = v24->StandardInput;
                v25 = v17->ProcessParameters;
                if ( (v25->WindowFlags & 0x400) == 0 )
                  ProcessParameters->StandardOutput = v25->StandardOutput;
                ProcessParameters->StandardError = v17->ProcessParameters->StandardError;
              }
            }
            if ( (a10 & 0x200) != 0 && (a10 & 0x10) == 0 )
              ProcessParameters->ConsoleFlags |= 1u;
            ProcessParameters->Flags |= v17->ProcessParameters->Flags & 0x100;
            if ( v20 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v31.Buffer);
            return ProcessParameters;
          }
        }
      }
    }
  }
LABEL_26:
  if ( ProcessParameters )
    RtlDestroyProcessParameters(ProcessParameters);
  BaseSetLastNTError((unsigned int)inited);
  return 0;
}

```

## disassembly

```asm
0x1800ef8f0  push    rbp
0x1800ef8f2  push    rbx
0x1800ef8f3  push    rsi
0x1800ef8f4  push    rdi
0x1800ef8f5  push    r12
0x1800ef8f7  push    r13
0x1800ef8f9  push    r14
0x1800ef8fb  push    r15
0x1800ef8fd  lea     rbp, [rsp-3A8h]
0x1800ef905  sub     rsp, 4A8h
0x1800ef90c  mov     rax, cs:__security_cookie
0x1800ef913  xor     rax, rsp
0x1800ef916  mov     [rbp+3E0h+var_50], rax
0x1800ef91d  mov     rax, [rbp+3E0h+arg_28]
0x1800ef924  mov     r13, r8
0x1800ef927  mov     r12, [rbp+3E0h+arg_20]
0x1800ef92e  mov     rdi, rdx
0x1800ef931  mov     rbx, [rbp+3E0h+arg_38]
0x1800ef938  xor     edx, edx; Val
0x1800ef93a  mov     r14, [rbp+3E0h+arg_40]
0x1800ef941  mov     r8d, 448h; Size
0x1800ef947  mov     [rsp+4E0h+var_4B0], rcx
0x1800ef94c  mov     rsi, r9
0x1800ef94f  lea     rcx, [rsp+4E0h+var_4A0]; void *
0x1800ef954  mov     [rsp+4E0h+SourceString], rax
0x1800ef959  mov     [rsp+4E0h+ProcessParameters], 0
0x1800ef962  call    memset_0
0x1800ef967  mov     r15, gs:60h
0x1800ef970  lea     rcx, [rbp+3E0h+DestinationString]; DestinationString
0x1800ef974  movups  xmm0, xmmword ptr [rdi]
0x1800ef977  mov     rdx, rsi; SourceString
0x1800ef97a  mov     [rbp+3E0h+var_420], rbx
0x1800ef97e  movdqu  [rbp+3E0h+var_440], xmm0
0x1800ef983  call    cs:__imp_RtlInitUnicodeStringEx
0x1800ef98a  nop     dword ptr [rax+rax+00h]
0x1800ef98f  mov     ebx, eax
0x1800ef991  test    eax, eax
0x1800ef993  js      loc_1800EFC33
0x1800ef999  mov     rdx, r13; SourceString
0x1800ef99c  lea     rcx, [rsp+4E0h+var_468]; DestinationString
0x1800ef9a1  call    cs:__imp_RtlInitUnicodeStringEx
0x1800ef9a8  nop     dword ptr [rax+rax+00h]
0x1800ef9ad  xor     r13d, r13d
0x1800ef9b0  mov     ebx, eax
0x1800ef9b2  test    eax, eax
0x1800ef9b4  js      loc_1800EFC33
0x1800ef9ba  mov     rdx, [rsp+4E0h+SourceString]; SourceString
0x1800ef9bf  lea     rcx, [rbp+3E0h+var_90]; DestinationString
0x1800ef9c6  call    cs:__imp_RtlInitUnicodeStringEx
0x1800ef9cd  nop     dword ptr [rax+rax+00h]
0x1800ef9d2  mov     ebx, eax
0x1800ef9d4  test    eax, eax
0x1800ef9d6  js      loc_1800EFC33
0x1800ef9dc  mov     rdx, r12; SourceString
0x1800ef9df  lea     rcx, [rbp+3E0h+var_450]; DestinationString
0x1800ef9e3  call    cs:__imp_RtlInitUnicodeStringEx
0x1800ef9ea  nop     dword ptr [rax+rax+00h]
0x1800ef9ef  mov     ebx, eax
0x1800ef9f1  test    eax, eax
0x1800ef9f3  js      loc_1800EFC33
0x1800ef9f9  mov     edi, [rbp+3E0h+arg_58]
0x1800ef9ff  mov     sil, r13b
0x1800efa02  lea     ebx, [r13+2]
0x1800efa06  test    r12, r12
0x1800efa09  jz      loc_1800EFBEB
0x1800efa0f  mov     rdx, [r14+10h]; SourceString
0x1800efa13  lea     rcx, [rbp+3E0h+var_3E0]; DestinationString
0x1800efa17  call    cs:__imp_RtlInitUnicodeStringEx
0x1800efa1e  nop     dword ptr [rax+rax+00h]
0x1800efa23  mov     ebx, eax
0x1800efa25  test    eax, eax
0x1800efa27  js      loc_1800EFC33
0x1800efa2d  mov     rdx, [r14+8]; SourceString
0x1800efa31  lea     rcx, [rbp+3E0h+var_3D0]; DestinationString
0x1800efa35  call    cs:__imp_RtlInitUnicodeStringEx
0x1800efa3c  nop     dword ptr [rax+rax+00h]
0x1800efa41  mov     ebx, eax
0x1800efa43  test    eax, eax
0x1800efa45  js      loc_1800EFC33
0x1800efa4b  mov     rax, [r14+48h]
0x1800efa4f  lea     rcx, [rbp+3E0h+var_3F0]; DestinationString
0x1800efa53  mov     rdx, [r14+18h]
0x1800efa57  mov     [rbp+3E0h+var_3B8], rax
0x1800efa5b  movzx   eax, word ptr [r14+42h]
0x1800efa60  mov     [rbp+3E0h+var_3C0], ax
0x1800efa64  mov     [rbp+3E0h+var_3BE], ax
0x1800efa68  test    rdx, rdx
0x1800efa6b  jnz     short loc_1800EFA72
0x1800efa6d  mov     rdx, [rsp+4E0h+var_4B0]; SourceString
0x1800efa72  call    cs:__imp_RtlInitUnicodeStringEx
0x1800efa79  nop     dword ptr [rax+rax+00h]
0x1800efa7e  mov     ebx, eax
0x1800efa80  test    eax, eax
0x1800efa82  js      loc_1800EFC33
0x1800efa88  mov     r8d, 1
0x1800efa8e  lea     rdx, [rsp+4E0h+var_4A0]
0x1800efa93  lea     rcx, [rsp+4E0h+ProcessParameters]
0x1800efa98  call    cs:__imp_RtlCreateProcessParametersWithTemplate
0x1800efa9f  nop     dword ptr [rax+rax+00h]
0x1800efaa4  mov     ebx, eax
0x1800efaa6  test    eax, eax
0x1800efaa8  js      loc_1800EFC33
0x1800efaae  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efab3  mov     ebx, 200h
0x1800efab8  mov     ecx, [r14+20h]
0x1800efabc  mov     r8d, [rbp+3E0h+arg_48]
0x1800efac3  mov     r9d, r8d
0x1800efac6  mov     [rax+88h], ecx
0x1800efacc  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efad1  mov     ecx, [r14+24h]
0x1800efad5  mov     [rax+8Ch], ecx
0x1800efadb  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efae0  mov     ecx, [r14+28h]
0x1800efae4  mov     [rax+90h], ecx
0x1800efaea  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efaef  mov     ecx, [r14+2Ch]
0x1800efaf3  mov     [rax+94h], ecx
0x1800efaf9  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efafe  mov     ecx, [r14+30h]
0x1800efb02  mov     [rax+98h], ecx
0x1800efb08  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efb0d  mov     ecx, [r14+34h]
0x1800efb11  mov     [rax+9Ch], ecx
0x1800efb17  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efb1c  mov     ecx, [r14+38h]
0x1800efb20  mov     [rax+0A0h], ecx
0x1800efb26  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efb2b  mov     ecx, [r14+3Ch]
0x1800efb2f  mov     [rax+0A4h], ecx
0x1800efb35  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efb3a  movzx   ecx, word ptr [r14+40h]
0x1800efb3f  mov     [rax+0A8h], ecx
0x1800efb45  and     r9d, ebx
0x1800efb48  jnz     loc_1800EFDBD
0x1800efb4e  mov     rax, [r15+20h]
0x1800efb52  mov     ecx, [rax+408h]
0x1800efb58  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efb5d  mov     [rax+408h], ecx
0x1800efb63  mov     r10d, 700h
0x1800efb69  mov     r11d, 100h
0x1800efb6f  test    [r14+3Ch], r10d
0x1800efb73  jnz     loc_1800EFD0E
0x1800efb79  mov     edx, r8d
0x1800efb7c  and     edx, 10h
0x1800efb7f  test    r8b, 8
0x1800efb83  jnz     loc_1800EFCFC
0x1800efb89  test    edx, edx
0x1800efb8b  jz      loc_1800EFC4F
0x1800efb91  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efb96  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFEh
0x1800efb9e  test    r9d, r9d
0x1800efba1  jnz     loc_1800EFE53
0x1800efba7  mov     rax, [r15+20h]
0x1800efbab  mov     rdx, [rsp+4E0h+ProcessParameters]
0x1800efbb0  mov     ecx, [rax+8]
0x1800efbb3  and     ecx, r11d
0x1800efbb6  or      [rdx+8], ecx
0x1800efbb9  test    sil, sil
0x1800efbbc  jnz     loc_1800EFDCE
0x1800efbc2  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efbc7  mov     rcx, [rbp+3E0h+var_50]
0x1800efbce  xor     rcx, rsp; StackCookie
0x1800efbd1  call    __security_check_cookie
0x1800efbd6  add     rsp, 4A8h
0x1800efbdd  pop     r15
0x1800efbdf  pop     r14
0x1800efbe1  pop     r13
0x1800efbe3  pop     r12
0x1800efbe5  pop     rdi
0x1800efbe6  pop     rsi
0x1800efbe7  pop     rbx
0x1800efbe8  pop     rbp
0x1800efbe9  retn
0x1800efbeb  cmp     [rbp+3E0h+arg_30], r13b
0x1800efbf2  jnz     loc_1800EFA0F
0x1800efbf8  bt      edi, 10h
0x1800efbfc  jb      loc_1800EFA0F
0x1800efc02  lea     rcx, [rbp+3E0h+var_450]
0x1800efc06  call    cs:__imp_LdrGetDllDirectory
0x1800efc0d  nop     dword ptr [rax+rax+00h]
0x1800efc12  cmp     [rbp+3E0h+var_450.Length], bx
0x1800efc16  ja      loc_1800EFD5F
0x1800efc1c  xor     edx, edx; SourceString
0x1800efc1e  lea     rcx, [rbp+3E0h+var_450]; DestinationString
0x1800efc22  call    cs:__imp_RtlInitUnicodeString
0x1800efc29  nop     dword ptr [rax+rax+00h]
0x1800efc2e  jmp     loc_1800EFA0F
0x1800efc33  mov     rcx, [rsp+4E0h+ProcessParameters]; ProcessParameters
0x1800efc38  test    rcx, rcx
0x1800efc3b  jnz     loc_1800EFE69
0x1800efc41  mov     ecx, ebx
0x1800efc43  call    BaseSetLastNTError
0x1800efc48  xor     eax, eax
0x1800efc4a  jmp     loc_1800EFBC7
0x1800efc4f  bt      r8d, 1Bh
0x1800efc54  jb      loc_1800EFD4D
0x1800efc5a  mov     r8, [rbp+3E0h+arg_60]
0x1800efc61  test    r8, r8
0x1800efc64  jz      short loc_1800EFC72
0x1800efc66  mov     rcx, [r8]
0x1800efc69  test    rcx, rcx
0x1800efc6c  jnz     loc_1800EFE26
0x1800efc72  mov     rcx, [rsp+4E0h+ProcessParameters]
0x1800efc77  mov     rax, qword ptr cs:xmmword_1803AB0B0
0x1800efc7e  mov     [rcx+10h], rax
0x1800efc82  mov     r8, [rsp+4E0h+ProcessParameters]
0x1800efc87  cmp     [r8+10h], r13
0x1800efc8b  jnz     short loc_1800EFC99
0x1800efc8d  mov     rax, [r15+20h]
0x1800efc91  mov     rcx, [rax+10h]
0x1800efc95  mov     [r8+10h], rcx
0x1800efc99  test    [r14+3Ch], r10d
0x1800efc9d  jnz     loc_1800EFB9E
0x1800efca3  cmp     [rbp+3E0h+arg_50], r13d
0x1800efcaa  jz      loc_1800EFB9E
0x1800efcb0  mov     rcx, [r15+20h]
0x1800efcb4  test    [rcx+0A4h], ebx
0x1800efcba  jnz     short loc_1800EFCC9
0x1800efcbc  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efcc1  mov     rcx, [rcx+20h]
0x1800efcc5  mov     [rax+20h], rcx
0x1800efcc9  mov     rcx, [r15+20h]
0x1800efccd  test    dword ptr [rcx+0A4h], 400h
0x1800efcd7  jnz     short loc_1800EFCE6
0x1800efcd9  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efcde  mov     rcx, [rcx+28h]
0x1800efce2  mov     [rax+28h], rcx
0x1800efce6  mov     rax, [r15+20h]
0x1800efcea  mov     rcx, [rax+30h]
0x1800efcee  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efcf3  mov     [rax+30h], rcx
0x1800efcf7  jmp     loc_1800EFB9E
0x1800efcfc  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efd01  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1800efd09  jmp     loc_1800EFB9E
0x1800efd0e  cmp     [rbp+3E0h+arg_68], r13
0x1800efd15  jnz     short loc_1800EFD21
0x1800efd17  test    [r14+3Ch], r11d
0x1800efd1b  jnz     loc_1800EFDFC
0x1800efd21  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efd26  mov     rcx, [r14+50h]
0x1800efd2a  mov     [rax+20h], rcx
0x1800efd2e  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efd33  mov     rcx, [r14+58h]
0x1800efd37  mov     [rax+28h], rcx
0x1800efd3b  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efd40  mov     rcx, [r14+60h]
0x1800efd44  mov     [rax+30h], rcx
0x1800efd48  jmp     loc_1800EFB79
0x1800efd4d  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efd52  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFDh
0x1800efd5a  jmp     loc_1800EFB9E
0x1800efd5f  cmp     eax, 0C0000023h
0x1800efd64  jnz     loc_1800EFC1C
0x1800efd6a  mov     rcx, gs:60h
0x1800efd73  xor     edx, edx; Flags
0x1800efd75  movzx   r8d, [rbp+3E0h+var_450.Length]; Size
0x1800efd7a  mov     rcx, [rcx+30h]; HeapHandle
0x1800efd7e  call    cs:__imp_RtlAllocateHeap
0x1800efd85  nop     dword ptr [rax+rax+00h]
0x1800efd8a  mov     [rbp+3E0h+var_450.Buffer], rax
0x1800efd8e  test    rax, rax
0x1800efd91  jz      short loc_1800EFDF2
0x1800efd93  movzx   eax, [rbp+3E0h+var_450.Length]
0x1800efd97  lea     rcx, [rbp+3E0h+var_450]
0x1800efd9b  mov     [rbp+3E0h+var_450.MaximumLength], ax
0x1800efd9f  call    cs:__imp_LdrGetDllDirectory
0x1800efda6  nop     dword ptr [rax+rax+00h]
0x1800efdab  mov     ebx, eax
0x1800efdad  test    eax, eax
0x1800efdaf  js      loc_1800EFC33
0x1800efdb5  mov     sil, 1
0x1800efdb8  jmp     loc_1800EFA0F
0x1800efdbd  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efdc2  mov     [rax+408h], r13d
0x1800efdc9  jmp     loc_1800EFB63
0x1800efdce  mov     rcx, gs:60h
0x1800efdd7  xor     edx, edx; Flags
0x1800efdd9  mov     r8, [rbp+3E0h+var_450.Buffer]; P
0x1800efddd  mov     rcx, [rcx+30h]; HeapHandle
0x1800efde1  call    cs:__imp_RtlFreeHeap
0x1800efde8  nop     dword ptr [rax+rax+00h]
0x1800efded  jmp     loc_1800EFBC2
0x1800efdf2  mov     ebx, 0C0000017h
0x1800efdf7  jmp     loc_1800EFC33
0x1800efdfc  test    dil, 4
0x1800efe00  jnz     loc_1800EFD21
0x1800efe06  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efe0b  mov     [rax+20h], r13
0x1800efe0f  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efe14  mov     [rax+28h], r13
0x1800efe18  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efe1d  mov     [rax+30h], r13
0x1800efe21  jmp     loc_1800EFB79
0x1800efe26  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efe2b  mov     rcx, [rcx]
0x1800efe2e  mov     [rax+10h], rcx
0x1800efe32  mov     rax, [rsp+4E0h+ProcessParameters]
0x1800efe37  or      dword ptr [rax+18h], 2
0x1800efe3b  cmp     [r8+8], r13b
  ... truncated ...
```
