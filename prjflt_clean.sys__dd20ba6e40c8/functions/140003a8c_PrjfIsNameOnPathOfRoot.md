# PrjfIsNameOnPathOfRoot

- ea: `0x140003a8c`
- end: `0x140003d93`
- name: `PrjfIsNameOnPathOfRoot`
- size: `775`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002d988`
- `0x14002e374`

## callees

- `0x140003a8c`
- `0x14000b1d0`
- `0x14000d128`
- `0x14000d448`
- `0x14003775c`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003bcd`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003c09`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003bcd`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140003c09`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003d2e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003d2e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003d6c`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140003d6c`
- `FLTMGR!FltGetFileNameInformation` at `0x140003b03`
- `FLTMGR!FltGetFileNameInformation` at `0x140003b03`
- `FLTMGR!FltReleaseResource` at `0x140003d42`
- `FLTMGR!FltReleaseResource` at `0x140003d42`
- `FLTMGR!FltAcquireResourceShared` at `0x140003b9d`
- `FLTMGR!FltAcquireResourceShared` at `0x140003b9d`
- `FLTMGR!FltGetInstanceContext` at `0x140003ac6`
- `FLTMGR!FltGetInstanceContext` at `0x140003ac6`
- `FLTMGR!FltReleaseContext` at `0x140003d57`
- `FLTMGR!FltReleaseContext` at `0x140003d57`

## pseudocode

```c
__int64 __fastcall PrjfIsNameOnPathOfRoot(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        _DWORD *a3,
        struct _UNICODE_STRING *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // esi
  UNICODE_STRING *p_Name; // r15
  char *v16; // rax
  char *v17; // rbx
  USHORT *v18; // r12
  int v19; // edx
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  int UnicodeString; // eax
  int v24; // edx
  int v25; // r8d
  PFLT_CONTEXT Context; // [rsp+B0h] [rbp+50h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+B8h] [rbp+58h] BYREF

  Context = 0;
  FileNameInformation = 0;
  if ( FltGetInstanceContext(Instance, &Context) < 0 || !Context )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7, v9, v10);
  *a3 = 0;
  a4->Length = 0;
  a4->Buffer = 0;
  v11 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
  v14 = v11;
  if ( v11 >= 0 )
  {
    p_Name = &FileNameInformation->Name;
    FltAcquireResourceShared((PERESOURCE)((char *)Context + 48));
    v14 = -1073741275;
    v16 = (char *)Context + 152;
    v17 = (char *)*((_QWORD *)Context + 19);
    while ( v17 != v16 )
    {
      v18 = (USHORT *)(v17 + 24);
      if ( RtlPrefixUnicodeString((PCUNICODE_STRING)(v17 + 24), p_Name, 1u) )
      {
        if ( p_Name->Length <= *v18 )
        {
          if ( p_Name->Length == *v18 )
            *a3 = 3;
          goto LABEL_22;
        }
        v20 = (unsigned __int64)*v18 >> 1;
        if ( p_Name->Buffer[v20] == 92 )
        {
          *a3 = 2;
          goto LABEL_22;
        }
      }
      else if ( RtlPrefixUnicodeString(p_Name, (PCUNICODE_STRING)(v17 + 24), 1u) )
      {
        if ( *v18 <= p_Name->Length
          || (v20 = (unsigned __int64)p_Name->Length >> 1, *(_WORD *)(*((_QWORD *)v17 + 4) + 2 * v20) == 92) )
        {
          *a3 = 1;
LABEL_22:
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( (BYTE1(xmmword_14001A3E0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = BYTE1(xmmword_14001A3E0) & 0x40;
            WPP_RECORDER_AND_TRACE_SF_sDZL(v20, v19, v21, *((_QWORD *)WPP_GLOBAL_Control + 8));
          }
          a4->MaximumLength = *((_WORD *)v17 + 13);
          UnicodeString = PrjfAllocateUnicodeString(1852197456, a4, v21, v22);
          v14 = UnicodeString;
          if ( UnicodeString >= 0 )
          {
            RtlCopyUnicodeString(a4, (PCUNICODE_STRING)(v17 + 24));
          }
          else
          {
            if ( (BYTE1(xmmword_14001A3D0) & 2) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v24) = BYTE1(xmmword_14001A3D0) & 2;
              LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                521,
                v24,
                v25,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                9,
                45,
                (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
                223,
                UnicodeString);
            }
            *a3 = 0;
          }
          break;
        }
      }
      v17 = *(char **)v17;
      v16 = (char *)Context + 152;
    }
    FltReleaseResource((PERESOURCE)((char *)Context + 48));
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 2;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      521,
      v12,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      9,
      43,
      (__int64)&WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      126,
      v11);
  }
  if ( Context )
    FltReleaseContext(Context);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return v14;
}

```

## disassembly

```asm
0x140003a8c  mov     [rsp-38h+arg_0], rbx
0x140003a91  push    rbp
0x140003a92  push    rsi
0x140003a93  push    rdi
0x140003a94  push    r12
0x140003a96  push    r13
0x140003a98  push    r14
0x140003a9a  push    r15
0x140003a9c  mov     rbp, rsp
0x140003a9f  sub     rsp, 60h
0x140003aa3  mov     rax, rdx
0x140003aa6  mov     [rbp+Context], 0
0x140003aae  mov     rbx, rcx
0x140003ab1  mov     [rbp+FileNameInformation], 0
0x140003ab9  mov     rcx, rax; Instance
0x140003abc  lea     rdx, [rbp+Context]; Context
0x140003ac0  mov     r13, r9
0x140003ac3  mov     rdi, r8
0x140003ac6  call    cs:__imp_FltGetInstanceContext
0x140003acd  nop     dword ptr [rax+rax+00h]
0x140003ad2  test    eax, eax
0x140003ad4  js      short loc_140003ADD
0x140003ad6  cmp     [rbp+Context], 0
0x140003adb  jnz     short loc_140003AE2
0x140003add  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003ae2  xor     eax, eax
0x140003ae4  mov     dword ptr [rdi], 0
0x140003aea  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140003aee  mov     [r13+0], ax
0x140003af3  mov     edx, 101h; NameOptions
0x140003af8  mov     qword ptr [r13+8], 0
0x140003b00  mov     rcx, rbx; CallbackData
0x140003b03  call    cs:__imp_FltGetFileNameInformation
0x140003b0a  nop     dword ptr [rax+rax+00h]
0x140003b0f  mov     esi, eax
0x140003b11  test    eax, eax
0x140003b13  jns     short loc_140003B8D
0x140003b15  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140003b1b  lea     r14, WPP_RECORDER_INITIALIZED
0x140003b22  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140003b29  setnz   r8b
0x140003b2d  and     dl, 2
0x140003b30  jnz     short loc_140003B3B
0x140003b32  test    r8b, r8b
0x140003b35  jz      loc_140003D4E
0x140003b3b  mov     r9, cs:WPP_GLOBAL_Control
0x140003b42  mov     ecx, 209h
0x140003b47  mov     dword ptr [rsp+60h+var_10], eax
0x140003b4b  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140003b52  mov     [rsp+60h+var_18], 97Eh
0x140003b5a  mov     [rsp+60h+var_20], rax
0x140003b5f  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140003b66  mov     r9, [r9+40h]
0x140003b6a  mov     [rsp+60h+var_28], rax
0x140003b6f  mov     [rsp+60h+var_30], 2Bh ; '+'
0x140003b76  mov     [rsp+60h+var_38], 9
0x140003b7e  mov     [rsp+60h+var_40], 2
0x140003b83  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140003b88  jmp     loc_140003D4E
0x140003b8d  mov     rcx, [rbp+Context]
0x140003b91  mov     r15, [rbp+FileNameInformation]
0x140003b95  add     rcx, 30h ; '0'; Resource
0x140003b99  add     r15, 8
0x140003b9d  call    cs:__imp_FltAcquireResourceShared
0x140003ba4  nop     dword ptr [rax+rax+00h]
0x140003ba9  mov     rax, [rbp+Context]
0x140003bad  mov     esi, 0C0000225h
0x140003bb2  add     rax, 98h
0x140003bb8  mov     rbx, [rax]
0x140003bbb  jmp     loc_140003C41
0x140003bc0  lea     r12, [rbx+18h]
0x140003bc4  mov     r8b, 1; CaseInSensitive
0x140003bc7  mov     rcx, r12; String1
0x140003bca  mov     rdx, r15; String2
0x140003bcd  call    cs:__imp_RtlPrefixUnicodeString
0x140003bd4  nop     dword ptr [rax+rax+00h]
0x140003bd9  test    al, al
0x140003bdb  jz      short loc_140003C00
0x140003bdd  movzx   eax, word ptr [r12]
0x140003be2  cmp     [r15], ax
0x140003be6  jbe     short loc_140003C4F
0x140003be8  mov     ecx, eax
0x140003bea  mov     rax, [r15+8]
0x140003bee  shr     rcx, 1
0x140003bf1  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140003bf6  jnz     short loc_140003C34
0x140003bf8  mov     dword ptr [rdi], 2
0x140003bfe  jmp     short loc_140003C5F
0x140003c00  mov     r8b, 1; CaseInSensitive
0x140003c03  mov     rdx, r12; String2
0x140003c06  mov     rcx, r15; String1
0x140003c09  call    cs:__imp_RtlPrefixUnicodeString
0x140003c10  nop     dword ptr [rax+rax+00h]
0x140003c15  test    al, al
0x140003c17  jz      short loc_140003C34
0x140003c19  movzx   eax, word ptr [r15]
0x140003c1d  cmp     [r12], ax
0x140003c22  jbe     short loc_140003C59
0x140003c24  mov     ecx, eax
0x140003c26  mov     rax, [rbx+20h]
0x140003c2a  shr     rcx, 1
0x140003c2d  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x140003c32  jz      short loc_140003C59
0x140003c34  mov     rax, [rbp+Context]
0x140003c38  mov     rbx, [rbx]
0x140003c3b  add     rax, 98h
0x140003c41  cmp     rbx, rax
0x140003c44  jnz     loc_140003BC0
0x140003c4a  jmp     loc_140003D3A
0x140003c4f  jnz     short loc_140003C5F
0x140003c51  mov     dword ptr [rdi], 3
0x140003c57  jmp     short loc_140003C5F
0x140003c59  mov     dword ptr [rdi], 1
0x140003c5f  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x140003c65  lea     r14, WPP_RECORDER_INITIALIZED
0x140003c6c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140003c73  setnz   r8b
0x140003c77  and     dl, 40h
0x140003c7a  jnz     short loc_140003C81
0x140003c7c  test    r8b, r8b
0x140003c7f  jz      short loc_140003C9C
0x140003c81  mov     r9, cs:WPP_GLOBAL_Control
0x140003c88  mov     eax, [rdi]
0x140003c8a  mov     [rsp+60h+var_8], eax
0x140003c8e  mov     [rsp+60h+var_10], r15
0x140003c93  mov     r9, [r9+40h]
0x140003c97  call    WPP_RECORDER_AND_TRACE_SF_sDZL
0x140003c9c  movzx   eax, word ptr [rbx+1Ah]
0x140003ca0  mov     rdx, r13
0x140003ca3  mov     ecx, 6E664A50h
0x140003ca8  mov     [r13+2], ax
0x140003cad  call    PrjfAllocateUnicodeString
0x140003cb2  mov     esi, eax
0x140003cb4  test    eax, eax
0x140003cb6  jns     short loc_140003D28
0x140003cb8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140003cbf  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140003cc5  setnz   r8b
0x140003cc9  and     dl, 2
0x140003ccc  jnz     short loc_140003CD3
0x140003cce  test    r8b, r8b
0x140003cd1  jz      short loc_140003D20
0x140003cd3  mov     r9, cs:WPP_GLOBAL_Control
0x140003cda  mov     ecx, 209h
0x140003cdf  mov     dword ptr [rsp+60h+var_10], eax
0x140003ce3  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140003cea  mov     [rsp+60h+var_18], 9DFh
0x140003cf2  mov     [rsp+60h+var_20], rax
0x140003cf7  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140003cfe  mov     r9, [r9+40h]
0x140003d02  mov     [rsp+60h+var_28], rax
0x140003d07  mov     [rsp+60h+var_30], 2Dh ; '-'
0x140003d0e  mov     [rsp+60h+var_38], 9
0x140003d16  mov     [rsp+60h+var_40], 2
0x140003d1b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140003d20  mov     dword ptr [rdi], 0
0x140003d26  jmp     short loc_140003D3A
0x140003d28  mov     rdx, r12; SourceString
0x140003d2b  mov     rcx, r13; DestinationString
0x140003d2e  call    cs:__imp_RtlCopyUnicodeString
0x140003d35  nop     dword ptr [rax+rax+00h]
0x140003d3a  mov     rcx, [rbp+Context]
0x140003d3e  add     rcx, 30h ; '0'; Resource
0x140003d42  call    cs:__imp_FltReleaseResource
0x140003d49  nop     dword ptr [rax+rax+00h]
0x140003d4e  mov     rcx, [rbp+Context]; Context
0x140003d52  test    rcx, rcx
0x140003d55  jz      short loc_140003D63
0x140003d57  call    cs:__imp_FltReleaseContext
0x140003d5e  nop     dword ptr [rax+rax+00h]
0x140003d63  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140003d67  test    rcx, rcx
0x140003d6a  jz      short loc_140003D78
0x140003d6c  call    cs:__imp_FltReleaseFileNameInformation
0x140003d73  nop     dword ptr [rax+rax+00h]
0x140003d78  mov     rbx, [rsp+60h+arg_0]
0x140003d80  mov     eax, esi
0x140003d82  add     rsp, 60h
0x140003d86  pop     r15
0x140003d88  pop     r14
0x140003d8a  pop     r13
0x140003d8c  pop     r12
0x140003d8e  pop     rdi
0x140003d8f  pop     rsi
0x140003d90  pop     rbp
0x140003d91  retn
```
