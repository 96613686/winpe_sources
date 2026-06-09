# WerpGetDebugger

- ea: `0x180051bc0`
- end: `0x1800520e6`
- name: `WerpGetDebugger`
- size: `1318`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003eb04`
- `0x18005193c`
- `0x180051bc0`
- `0x1800520ec`
- `0x180052114`
- `0x180052140`
- `0x1800529d0`
- `0x18008275d`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180051e00`
- `ntdll!DbgPrintEx` at `0x180051fc8`
- `ntdll!DbgPrintEx` at `0x180051ffc`
- `ntdll!DbgPrintEx` at `0x180052031`
- `ntdll!DbgPrintEx` at `0x180052066`
- `ntdll!DbgPrintEx` at `0x180052094`
- `ntdll!DbgPrintEx` at `0x180051e00`
- `ntdll!DbgPrintEx` at `0x180051fc8`
- `ntdll!DbgPrintEx` at `0x180051ffc`
- `ntdll!DbgPrintEx` at `0x180052031`
- `ntdll!DbgPrintEx` at `0x180052066`
- `ntdll!DbgPrintEx` at `0x180052094`
- `ntdll!NtQueryValueKey` at `0x180051d9f`
- `ntdll!NtQueryValueKey` at `0x180051e5c`
- `ntdll!NtQueryValueKey` at `0x180051ec1`
- `ntdll!NtQueryValueKey` at `0x180051f5c`
- `ntdll!NtQueryValueKey` at `0x180051d9f`
- `ntdll!NtQueryValueKey` at `0x180051e5c`
- `ntdll!NtQueryValueKey` at `0x180051ec1`
- `ntdll!NtQueryValueKey` at `0x180051f5c`
- `ntdll!NtOpenKey` at `0x180051d41`
- `ntdll!NtOpenKey` at `0x180051d41`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180051cc0`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180051cc0`

## string_xrefs

- `0x180051de6`: `WER/CrashAPI/%u:%u: ERROR Stringcchcopy failed while copying the debugger path 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpGetDebugger(HANDLE ProcessHandle, unsigned int *a2)
{
  unsigned int *v4; // rax
  _OWORD *v5; // rcx
  __int64 v6; // rdx
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  int *v18; // rbx
  unsigned int v19; // edi
  int IsProtectedProcess; // r15d
  __int64 *v21; // rax
  void **v22; // rax
  NTSTATUS v23; // edi
  struct _UNICODE_STRING *v24; // rdx
  int *v25; // r14
  int v26; // eax
  int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  int v30; // eax
  __int64 v31; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v34[640]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ResultLength; // [rsp+2F0h] [rbp+1F0h] BYREF
  HANDLE KeyHandle; // [rsp+300h] [rbp+200h] BYREF
  int *v37; // [rsp+308h] [rbp+208h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( ProcessHandle && a2 )
  {
    memset_0(v34, 0, 0x250u);
    v4 = a2;
    v5 = v34;
    v6 = 4;
    do
    {
      v7 = v5[1];
      *(_OWORD *)v4 = *v5;
      v8 = v5[2];
      *((_OWORD *)v4 + 1) = v7;
      v9 = v5[3];
      *((_OWORD *)v4 + 2) = v8;
      v10 = v5[4];
      *((_OWORD *)v4 + 3) = v9;
      v11 = v5[5];
      *((_OWORD *)v4 + 4) = v10;
      v12 = v5[6];
      *((_OWORD *)v4 + 5) = v11;
      v13 = v5[7];
      v5 += 8;
      *((_OWORD *)v4 + 6) = v12;
      *((_OWORD *)v4 + 7) = v13;
      v4 += 32;
      --v6;
    }
    while ( v6 );
    v14 = v5[1];
    *(_OWORD *)v4 = *v5;
    v15 = v5[2];
    *((_OWORD *)v4 + 1) = v14;
    v16 = v5[3];
    *((_OWORD *)v4 + 2) = v15;
    v17 = v5[4];
    *((_OWORD *)v4 + 3) = v16;
    *((_OWORD *)v4 + 4) = v17;
    v37 = (int *)VirtualAlloc(0, 0x25Au, 0x1000u, 4u);
    v18 = v37;
    if ( v37 )
    {
      IsProtectedProcess = WerpIsProtectedProcess(ProcessHandle);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      v21 = &qword_180086508;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( !IsProtectedProcess )
        v21 = &qword_1800864F8;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v21;
      v22 = (void **)tlx::replace<tlx::file_handle_traits>(&KeyHandle);
      v23 = NtOpenKey(v22, 1u, &ObjectAttributes);
      if ( v23 >= 0 )
      {
        memset_0(v18, 0, 0x25Au);
        v24 = (struct _UNICODE_STRING *)L"\"$";
        if ( !IsProtectedProcess )
          v24 = (struct _UNICODE_STRING *)&stru_1800864D8;
        if ( NtQueryValueKey(KeyHandle, v24, KeyValuePartialInformation, v18, 0x25Au, &ResultLength) >= 0 && v18[1] == 1 )
        {
          v25 = v18 + 3;
          v26 = StringCchCopyW((wchar_t *)a2 + 2, 0x125u, (const wchar_t *)v18 + 6);
          v19 = v26;
          if ( v26 >= 0 )
          {
            *a2 |= 1u;
            if ( IsProtectedProcess )
            {
              *a2 |= 0x7Cu;
              memset_0(v18, 0, 0x25Au);
              if ( NtQueryValueKey(
                     KeyHandle,
                     (PUNICODE_STRING)&stru_1800864C8,
                     KeyValuePartialInformation,
                     v18,
                     0x25Au,
                     &ResultLength) >= 0
                && v18[1] == 4 )
              {
                *a2 = *a2 & 0xFFFFFFFB | (*v25 == 0 ? 4 : 0);
              }
              if ( (*(_BYTE *)a2 & 4) != 0 )
              {
                memset_0(v18, 0, 0x25Au);
                if ( NtQueryValueKey(
                       KeyHandle,
                       (PUNICODE_STRING)&stru_1800864E8,
                       KeyValuePartialInformation,
                       v18,
                       0x25Au,
                       &ResultLength) >= 0
                  && v18[1] == 4 )
                {
                  v27 = *v25;
                  if ( !*v25 || v27 == 1 || v27 == 2 || v27 == 3 || v27 == 4 || v27 == 5 || v27 == 6 || v27 == 7 )
                  {
                    *a2 ^= (*a2 ^ (8 * v27)) & 0x78;
                  }
                  else
                  {
                    v28 = *a2;
                    if ( v27 == 0x80000000 )
                      v29 = v28 & 0xFFFFFF87 | 0x70;
                    else
                      v29 = v28 | 0x78;
                    *a2 = v29;
                  }
                }
              }
            }
            memset_0(v18, 0, 0x25Au);
            if ( NtQueryValueKey(
                   KeyHandle,
                   (PUNICODE_STRING)&stru_1800864A8,
                   KeyValuePartialInformation,
                   v18,
                   0x25Au,
                   &ResultLength) >= 0
              && (v18[1] == 1 && *(_WORD *)v25 == 49 || v18[1] == 4 && *v25)
              && !(unsigned int)WerpIsProcessInAeDebugExclusionList(ProcessHandle) )
            {
              v30 = 2;
            }
            else
            {
              v30 = 0;
            }
            *a2 &= ~2u;
            *a2 |= v30;
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.Available: %u\n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              4549,
              *a2 & 1);
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.AutoEnabled: %u\n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              4550,
              (*a2 >> 1) & 1);
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.Protected: %u\n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              4551,
              (*a2 >> 2) & 1);
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.ProtectionLevel: %08X\n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              4552,
              (*a2 >> 3) & 0xF);
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.Debugger: %S\n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              4553,
              (const wchar_t *)a2 + 2);
            v19 = 0;
          }
          else
          {
            DbgPrintEx(
              0x96u,
              0,
              "WER/CrashAPI/%u:%u: ERROR Stringcchcopy failed while copying the debugger path 0x%x\n",
              NtCurrentTeb()->ClientId.UniqueProcess,
              4448,
              v26);
          }
        }
        else
        {
          v19 = -2147023728;
        }
      }
      else
      {
        v19 = v23 | 0x10000000;
      }
    }
    else
    {
      v19 = -2147024882;
    }
    utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&v37);
    tlx::file_handle_traits::operator()(v31, KeyHandle);
    return v19;
  }
  else
  {
    tlx::file_handle_traits::operator()(ProcessHandle, 0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180051bc0  mov     [rsp-8+arg_8], rbx
0x180051bc5  push    rbp
0x180051bc6  push    rsi
0x180051bc7  push    rdi
0x180051bc8  push    r12
0x180051bca  push    r13
0x180051bcc  push    r14
0x180051bce  push    r15
0x180051bd0  lea     rbp, [rsp-1B0h]
0x180051bd8  sub     rsp, 2B0h
0x180051bdf  xor     r14d, r14d
0x180051be2  xorps   xmm0, xmm0
0x180051be5  mov     [rbp+1E0h+KeyHandle], r14
0x180051bec  mov     rsi, rdx
0x180051bef  mov     [rbp+1E0h+arg_0], r14d
0x180051bf6  mov     r12, rcx
0x180051bf9  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180051bfe  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x180051c03  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051c08  test    rcx, rcx
0x180051c0b  jz      loc_1800520BE
0x180051c11  test    rdx, rdx
0x180051c14  jz      loc_1800520BE
0x180051c1a  xor     edx, edx; Val
0x180051c1c  lea     rcx, [rsp+2E0h+var_280]; void *
0x180051c21  mov     r8d, 250h; Size
0x180051c27  call    memset_0
0x180051c2c  lea     r9d, [r14+4]; flProtect
0x180051c30  mov     rax, rsi
0x180051c33  lea     rcx, [rsp+2E0h+var_280]
0x180051c38  mov     edx, r9d
0x180051c3b  lea     r8d, [r9+7Ch]
0x180051c3f  movups  xmm0, xmmword ptr [rcx]
0x180051c42  movups  xmm1, xmmword ptr [rcx+10h]
0x180051c46  movups  xmmword ptr [rax], xmm0
0x180051c49  movups  xmm0, xmmword ptr [rcx+20h]
0x180051c4d  movups  xmmword ptr [rax+10h], xmm1
0x180051c51  movups  xmm1, xmmword ptr [rcx+30h]
0x180051c55  movups  xmmword ptr [rax+20h], xmm0
0x180051c59  movups  xmm0, xmmword ptr [rcx+40h]
0x180051c5d  movups  xmmword ptr [rax+30h], xmm1
0x180051c61  movups  xmm1, xmmword ptr [rcx+50h]
0x180051c65  movups  xmmword ptr [rax+40h], xmm0
0x180051c69  movups  xmm0, xmmword ptr [rcx+60h]
0x180051c6d  movups  xmmword ptr [rax+50h], xmm1
0x180051c71  movups  xmm1, xmmword ptr [rcx+70h]
0x180051c75  add     rcx, r8
0x180051c78  movups  xmmword ptr [rax+60h], xmm0
0x180051c7c  movups  xmmword ptr [rax+70h], xmm1
0x180051c80  add     rax, r8
0x180051c83  sub     rdx, 1
0x180051c87  jnz     short loc_180051C3F
0x180051c89  movups  xmm0, xmmword ptr [rcx]
0x180051c8c  mov     r13d, 25Ah
0x180051c92  mov     r8d, 1000h; flAllocationType
0x180051c98  movups  xmm1, xmmword ptr [rcx+10h]
0x180051c9c  mov     edx, r13d; dwSize
0x180051c9f  movups  xmmword ptr [rax], xmm0
0x180051ca2  movups  xmm0, xmmword ptr [rcx+20h]
0x180051ca6  movups  xmmword ptr [rax+10h], xmm1
0x180051caa  movups  xmm1, xmmword ptr [rcx+30h]
0x180051cae  movups  xmmword ptr [rax+20h], xmm0
0x180051cb2  movups  xmm0, xmmword ptr [rcx+40h]
0x180051cb6  xor     ecx, ecx; lpAddress
0x180051cb8  movups  xmmword ptr [rax+30h], xmm1
0x180051cbc  movups  xmmword ptr [rax+40h], xmm0
0x180051cc0  call    cs:__imp_VirtualAlloc
0x180051cc7  nop     dword ptr [rax+rax+00h]
0x180051ccc  mov     [rbp+1E0h+arg_18], rax
0x180051cd3  mov     rbx, rax
0x180051cd6  test    rax, rax
0x180051cd9  jnz     short loc_180051CE5
0x180051cdb  mov     edi, 8007000Eh
0x180051ce0  jmp     loc_1800520A2
0x180051ce5  mov     rcx, r12; ProcessHandle
0x180051ce8  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x180051ced  mov     r15d, eax
0x180051cf0  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180051cf8  lea     rcx, qword_1800864F8
0x180051cff  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x180051d04  xorps   xmm0, xmm0
0x180051d07  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180051d0f  test    r15d, r15d
0x180051d12  lea     rax, qword_180086508
0x180051d19  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180051d1f  cmovz   rax, rcx
0x180051d23  lea     rcx, [rbp+1E0h+KeyHandle]
0x180051d2a  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180051d2f  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180051d34  mov     rcx, rax; KeyHandle
0x180051d37  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180051d3c  mov     edx, 1; DesiredAccess
0x180051d41  call    cs:__imp_NtOpenKey
0x180051d48  nop     dword ptr [rax+rax+00h]
0x180051d4d  mov     edi, eax
0x180051d4f  test    eax, eax
0x180051d51  jns     short loc_180051D5C
0x180051d53  bts     edi, 1Ch
0x180051d57  jmp     loc_1800520A2
0x180051d5c  mov     r8, r13; Size
0x180051d5f  xor     edx, edx; Val
0x180051d61  mov     rcx, rbx; void *
0x180051d64  call    memset_0
0x180051d69  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180051d70  lea     rax, stru_1800864D8
0x180051d77  test    r15d, r15d
0x180051d7a  lea     rdx, asc_1800864B8; "\"$"
0x180051d81  mov     r9, rbx; KeyValueInformation
0x180051d84  mov     r8d, 2; KeyValueInformationClass
0x180051d8a  cmovz   rdx, rax; ValueName
0x180051d8e  lea     rax, [rbp+1E0h+arg_0]
0x180051d95  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180051d9a  mov     [rsp+2E0h+Length], r13d; Length
0x180051d9f  call    cs:__imp_NtQueryValueKey
0x180051da6  nop     dword ptr [rax+rax+00h]
0x180051dab  test    eax, eax
0x180051dad  jns     short loc_180051DB9
0x180051daf  mov     edi, 80070490h
0x180051db4  jmp     loc_1800520A2
0x180051db9  cmp     dword ptr [rbx+4], 1
0x180051dbd  jnz     short loc_180051DAF
0x180051dbf  lea     r13, [rsi+4]
0x180051dc3  mov     edx, 125h; unsigned __int64
0x180051dc8  lea     r14, [rbx+0Ch]
0x180051dcc  mov     rcx, r13; wchar_t *
0x180051dcf  mov     r8, r14; wchar_t *
0x180051dd2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180051dd7  mov     edi, eax
0x180051dd9  test    eax, eax
0x180051ddb  jns     short loc_180051E11
0x180051ddd  mov     r9, gs:40h
0x180051de6  lea     r8, aWerCrashapiUUE_5; "WER/CrashAPI/%u:%u: ERROR Stringcchcopy"...
0x180051ded  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180051df1  xor     edx, edx; Level
0x180051df3  mov     ecx, 96h; ComponentId
0x180051df8  mov     [rsp+2E0h+Length], 1160h
0x180051e00  call    cs:__imp_DbgPrintEx
0x180051e07  nop     dword ptr [rax+rax+00h]
0x180051e0c  jmp     loc_1800520A2
0x180051e11  or      dword ptr [rsi], 1
0x180051e14  mov     edi, 25Ah
0x180051e19  test    r15d, r15d
0x180051e1c  jz      loc_180051F25
0x180051e22  or      dword ptr [rsi], 7Ch
0x180051e25  mov     r8d, edi; Size
0x180051e28  xor     edx, edx; Val
0x180051e2a  mov     rcx, rbx; void *
0x180051e2d  call    memset_0
0x180051e32  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180051e39  lea     rax, [rbp+1E0h+arg_0]
0x180051e40  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180051e45  lea     rdx, stru_1800864C8; ValueName
0x180051e4c  mov     r15d, 2
0x180051e52  mov     [rsp+2E0h+Length], edi; Length
0x180051e56  mov     r9, rbx; KeyValueInformation
0x180051e59  mov     r8d, r15d; KeyValueInformationClass
0x180051e5c  call    cs:__imp_NtQueryValueKey
0x180051e63  nop     dword ptr [rax+rax+00h]
0x180051e68  test    eax, eax
0x180051e6a  js      short loc_180051E87
0x180051e6c  cmp     dword ptr [rbx+4], 4
0x180051e70  jnz     short loc_180051E87
0x180051e72  mov     eax, [r14]
0x180051e75  neg     eax
0x180051e77  mov     eax, [rsi]
0x180051e79  sbb     ecx, ecx
0x180051e7b  and     eax, 0FFFFFFFBh
0x180051e7e  not     ecx
0x180051e80  and     ecx, 4
0x180051e83  or      ecx, eax
0x180051e85  mov     [rsi], ecx
0x180051e87  test    byte ptr [rsi], 4
0x180051e8a  jz      loc_180051F2B
0x180051e90  mov     r8, rdi; Size
0x180051e93  xor     edx, edx; Val
0x180051e95  mov     rcx, rbx; void *
0x180051e98  call    memset_0
0x180051e9d  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180051ea4  lea     rax, [rbp+1E0h+arg_0]
0x180051eab  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180051eb0  lea     rdx, stru_1800864E8; ValueName
0x180051eb7  mov     r9, rbx; KeyValueInformation
0x180051eba  mov     [rsp+2E0h+Length], edi; Length
0x180051ebe  mov     r8d, r15d; KeyValueInformationClass
0x180051ec1  call    cs:__imp_NtQueryValueKey
0x180051ec8  nop     dword ptr [rax+rax+00h]
0x180051ecd  test    eax, eax
0x180051ecf  js      short loc_180051F2B
0x180051ed1  cmp     dword ptr [rbx+4], 4
0x180051ed5  jnz     short loc_180051F2B
0x180051ed7  mov     eax, [r14]
0x180051eda  test    eax, eax
0x180051edc  jz      short loc_180051F19
0x180051ede  cmp     eax, 1
0x180051ee1  jz      short loc_180051F19
0x180051ee3  cmp     eax, r15d
0x180051ee6  jz      short loc_180051F19
0x180051ee8  cmp     eax, 3
0x180051eeb  jz      short loc_180051F19
0x180051eed  cmp     eax, 4
0x180051ef0  jz      short loc_180051F19
0x180051ef2  cmp     eax, 5
0x180051ef5  jz      short loc_180051F19
0x180051ef7  cmp     eax, 6
0x180051efa  jz      short loc_180051F19
0x180051efc  cmp     eax, 7
0x180051eff  jz      short loc_180051F19
0x180051f01  mov     ecx, [rsi]
0x180051f03  cmp     eax, 80000000h
0x180051f08  jz      short loc_180051F0F
0x180051f0a  or      ecx, 78h
0x180051f0d  jmp     short loc_180051F15
0x180051f0f  and     ecx, 0FFFFFFF7h
0x180051f12  or      ecx, 70h
0x180051f15  mov     [rsi], ecx
0x180051f17  jmp     short loc_180051F2B
0x180051f19  shl     eax, 3
0x180051f1c  xor     eax, [rsi]
0x180051f1e  and     eax, 78h
0x180051f21  xor     [rsi], eax
0x180051f23  jmp     short loc_180051F2B
0x180051f25  mov     r15d, 2
0x180051f2b  mov     r8, rdi; Size
0x180051f2e  xor     edx, edx; Val
0x180051f30  mov     rcx, rbx; void *
0x180051f33  call    memset_0
0x180051f38  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180051f3f  lea     rax, [rbp+1E0h+arg_0]
0x180051f46  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180051f4b  lea     rdx, stru_1800864A8; ValueName
0x180051f52  mov     r9, rbx; KeyValueInformation
0x180051f55  mov     [rsp+2E0h+Length], edi; Length
0x180051f59  mov     r8d, r15d; KeyValueInformationClass
0x180051f5c  call    cs:__imp_NtQueryValueKey
0x180051f63  nop     dword ptr [rax+rax+00h]
0x180051f68  test    eax, eax
0x180051f6a  js      short loc_180051F96
0x180051f6c  cmp     dword ptr [rbx+4], 1
0x180051f70  jnz     short loc_180051F79
0x180051f72  cmp     word ptr [r14], 31h ; '1'
0x180051f77  jz      short loc_180051F85
0x180051f79  cmp     dword ptr [rbx+4], 4
0x180051f7d  jnz     short loc_180051F96
0x180051f7f  cmp     dword ptr [r14], 0
0x180051f83  jz      short loc_180051F96
0x180051f85  mov     rcx, r12; ProcessHandle
0x180051f88  call    WerpIsProcessInAeDebugExclusionList
0x180051f8d  test    eax, eax
0x180051f8f  jnz     short loc_180051F96
0x180051f91  mov     eax, r15d
0x180051f94  jmp     short loc_180051F98
0x180051f96  xor     eax, eax
0x180051f98  and     dword ptr [rsi], 0FFFFFFFDh
0x180051f9b  lea     r8, aWerCrashapiUUT_2; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180051fa2  or      [rsi], eax
0x180051fa4  mov     ebx, 96h
0x180051fa9  mov     eax, [rsi]
0x180051fab  mov     edx, r15d; Level
0x180051fae  mov     r9, gs:40h
0x180051fb7  and     eax, 1
0x180051fba  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180051fbe  mov     ecx, ebx; ComponentId
0x180051fc0  mov     [rsp+2E0h+Length], 11C5h
0x180051fc8  call    cs:__imp_DbgPrintEx
0x180051fcf  nop     dword ptr [rax+rax+00h]
0x180051fd4  mov     eax, [rsi]
0x180051fd6  lea     r8, aWerCrashapiUUT_5; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180051fdd  mov     r9, gs:40h
0x180051fe6  mov     edx, r15d; Level
0x180051fe9  shr     eax, 1
0x180051feb  mov     ecx, ebx; ComponentId
0x180051fed  and     eax, 1
0x180051ff0  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180051ff4  mov     [rsp+2E0h+Length], 11C6h
0x180051ffc  call    cs:__imp_DbgPrintEx
0x180052003  nop     dword ptr [rax+rax+00h]
0x180052008  mov     eax, [rsi]
0x18005200a  lea     r8, aWerCrashapiUUT_1; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052011  mov     r9, gs:40h
0x18005201a  mov     edx, r15d; Level
0x18005201d  shr     eax, 2
0x180052020  mov     ecx, ebx; ComponentId
0x180052022  and     eax, 1
0x180052025  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180052029  mov     [rsp+2E0h+Length], 11C7h
0x180052031  call    cs:__imp_DbgPrintEx
0x180052038  nop     dword ptr [rax+rax+00h]
0x18005203d  mov     eax, [rsi]
0x18005203f  lea     r8, aWerCrashapiUUT_3; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052046  mov     r9, gs:40h
0x18005204f  mov     edx, r15d; Level
0x180052052  shr     eax, 3
0x180052055  mov     ecx, ebx; ComponentId
0x180052057  and     eax, 0Fh
0x18005205a  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x18005205e  mov     [rsp+2E0h+Length], 11C8h
0x180052066  call    cs:__imp_DbgPrintEx
0x18005206d  nop     dword ptr [rax+rax+00h]
0x180052072  mov     r9, gs:40h
0x18005207b  lea     r8, aWerCrashapiUUT_4; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
  ... truncated ...
```
