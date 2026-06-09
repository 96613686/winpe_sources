# WerpGetDebugger

- ea: `0x180052a00`
- end: `0x180052ed6`
- name: `WerpGetDebugger`
- size: `1238`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003c390`
- `0x18004e1e4`
- `0x18004e8b8`
- `0x18004ec94`
- `0x180052a00`
- `0x180052edc`
- `0x180052f00`
- `0x18007a7dd`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180052c2e`
- `ntdll!DbgPrintEx` at `0x180052dde`
- `ntdll!DbgPrintEx` at `0x180052e0c`
- `ntdll!DbgPrintEx` at `0x180052e3b`
- `ntdll!DbgPrintEx` at `0x180052e6a`
- `ntdll!DbgPrintEx` at `0x180052e92`
- `ntdll!DbgPrintEx` at `0x180052c2e`
- `ntdll!DbgPrintEx` at `0x180052dde`
- `ntdll!DbgPrintEx` at `0x180052e0c`
- `ntdll!DbgPrintEx` at `0x180052e3b`
- `ntdll!DbgPrintEx` at `0x180052e6a`
- `ntdll!DbgPrintEx` at `0x180052e92`
- `ntdll!NtQueryValueKey` at `0x180052bd3`
- `ntdll!NtQueryValueKey` at `0x180052c84`
- `ntdll!NtQueryValueKey` at `0x180052ce3`
- `ntdll!NtQueryValueKey` at `0x180052d78`
- `ntdll!NtQueryValueKey` at `0x180052bd3`
- `ntdll!NtQueryValueKey` at `0x180052c84`
- `ntdll!NtQueryValueKey` at `0x180052ce3`
- `ntdll!NtQueryValueKey` at `0x180052d78`
- `ntdll!NtOpenKey` at `0x180052b7b`
- `ntdll!NtOpenKey` at `0x180052b7b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180052b00`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180052b00`

## string_xrefs

- `0x180052c14`: `WER/CrashAPI/%u:%u: ERROR Stringcchcopy failed while copying the debugger path 0x%x\n`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v33[640]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ResultLength; // [rsp+2F0h] [rbp+1F0h] BYREF
  HANDLE KeyHandle; // [rsp+300h] [rbp+200h] BYREF
  int *v36; // [rsp+308h] [rbp+208h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !ProcessHandle || !a2 )
    return 2147942487LL;
  memset_0(v33, 0, 0x250u);
  v4 = a2;
  v5 = v33;
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
  v36 = (int *)VirtualAlloc(0, 0x25Au, 0x1000u, 4u);
  v18 = v36;
  if ( v36 )
  {
    IsProtectedProcess = WerpIsProtectedProcess(ProcessHandle);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    v21 = &qword_18007E508;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( !IsProtectedProcess )
      v21 = &qword_18007E4F8;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v21;
    v22 = (void **)tlx::replace<tlx::file_handle_traits>(&KeyHandle);
    v23 = NtOpenKey(v22, 1u, &ObjectAttributes);
    if ( v23 >= 0 )
    {
      memset_0(v18, 0, 0x25Au);
      v24 = (struct _UNICODE_STRING *)L"\"$";
      if ( !IsProtectedProcess )
        v24 = (struct _UNICODE_STRING *)&stru_18007E4D8;
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
                   (PUNICODE_STRING)&stru_18007E4C8,
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
                     (PUNICODE_STRING)&stru_18007E4E8,
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
                 (PUNICODE_STRING)&stru_18007E4A8,
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
  utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(&v36);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&KeyHandle);
  return v19;
}

```

## disassembly

```asm
0x180052a00  mov     [rsp-8+arg_8], rbx
0x180052a05  push    rbp
0x180052a06  push    rsi
0x180052a07  push    rdi
0x180052a08  push    r12
0x180052a0a  push    r13
0x180052a0c  push    r14
0x180052a0e  push    r15
0x180052a10  lea     rbp, [rsp-1B0h]
0x180052a18  sub     rsp, 2B0h
0x180052a1f  xor     r14d, r14d
0x180052a22  xorps   xmm0, xmm0
0x180052a25  mov     [rbp+1E0h+KeyHandle], r14
0x180052a2c  mov     rsi, rdx
0x180052a2f  mov     [rbp+1E0h+arg_0], r14d
0x180052a36  mov     r12, rcx
0x180052a39  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x180052a3e  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x180052a43  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180052a48  test    rcx, rcx
0x180052a4b  jz      loc_180052EB6
0x180052a51  test    rdx, rdx
0x180052a54  jz      loc_180052EB6
0x180052a5a  xor     edx, edx; Val
0x180052a5c  lea     rcx, [rsp+2E0h+var_280]; void *
0x180052a61  mov     r8d, 250h; Size
0x180052a67  call    memset_0
0x180052a6c  lea     r9d, [r14+4]; flProtect
0x180052a70  mov     rax, rsi
0x180052a73  lea     rcx, [rsp+2E0h+var_280]
0x180052a78  mov     edx, r9d
0x180052a7b  lea     r8d, [r9+7Ch]
0x180052a7f  movups  xmm0, xmmword ptr [rcx]
0x180052a82  movups  xmm1, xmmword ptr [rcx+10h]
0x180052a86  movups  xmmword ptr [rax], xmm0
0x180052a89  movups  xmm0, xmmword ptr [rcx+20h]
0x180052a8d  movups  xmmword ptr [rax+10h], xmm1
0x180052a91  movups  xmm1, xmmword ptr [rcx+30h]
0x180052a95  movups  xmmword ptr [rax+20h], xmm0
0x180052a99  movups  xmm0, xmmword ptr [rcx+40h]
0x180052a9d  movups  xmmword ptr [rax+30h], xmm1
0x180052aa1  movups  xmm1, xmmword ptr [rcx+50h]
0x180052aa5  movups  xmmword ptr [rax+40h], xmm0
0x180052aa9  movups  xmm0, xmmword ptr [rcx+60h]
0x180052aad  movups  xmmword ptr [rax+50h], xmm1
0x180052ab1  movups  xmm1, xmmword ptr [rcx+70h]
0x180052ab5  add     rcx, r8
0x180052ab8  movups  xmmword ptr [rax+60h], xmm0
0x180052abc  movups  xmmword ptr [rax+70h], xmm1
0x180052ac0  add     rax, r8
0x180052ac3  sub     rdx, 1
0x180052ac7  jnz     short loc_180052A7F
0x180052ac9  movups  xmm0, xmmword ptr [rcx]
0x180052acc  mov     r13d, 25Ah
0x180052ad2  mov     r8d, 1000h; flAllocationType
0x180052ad8  movups  xmm1, xmmword ptr [rcx+10h]
0x180052adc  mov     edx, r13d; dwSize
0x180052adf  movups  xmmword ptr [rax], xmm0
0x180052ae2  movups  xmm0, xmmword ptr [rcx+20h]
0x180052ae6  movups  xmmword ptr [rax+10h], xmm1
0x180052aea  movups  xmm1, xmmword ptr [rcx+30h]
0x180052aee  movups  xmmword ptr [rax+20h], xmm0
0x180052af2  movups  xmm0, xmmword ptr [rcx+40h]
0x180052af6  xor     ecx, ecx; lpAddress
0x180052af8  movups  xmmword ptr [rax+30h], xmm1
0x180052afc  movups  xmmword ptr [rax+40h], xmm0
0x180052b00  call    cs:__imp_VirtualAlloc
0x180052b06  mov     [rbp+1E0h+arg_18], rax
0x180052b0d  mov     rbx, rax
0x180052b10  test    rax, rax
0x180052b13  jnz     short loc_180052B1F
0x180052b15  mov     edi, 8007000Eh
0x180052b1a  jmp     loc_180052E9A
0x180052b1f  mov     rcx, r12; ProcessHandle
0x180052b22  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x180052b27  mov     r15d, eax
0x180052b2a  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x180052b32  lea     rcx, qword_18007E4F8
0x180052b39  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x180052b3e  xorps   xmm0, xmm0
0x180052b41  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x180052b49  test    r15d, r15d
0x180052b4c  lea     rax, qword_18007E508
0x180052b53  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180052b59  cmovz   rax, rcx
0x180052b5d  lea     rcx, [rbp+1E0h+KeyHandle]
0x180052b64  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rax
0x180052b69  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180052b6e  mov     rcx, rax; KeyHandle
0x180052b71  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x180052b76  mov     edx, 1; DesiredAccess
0x180052b7b  call    cs:__imp_NtOpenKey
0x180052b81  mov     edi, eax
0x180052b83  test    eax, eax
0x180052b85  jns     short loc_180052B90
0x180052b87  bts     edi, 1Ch
0x180052b8b  jmp     loc_180052E9A
0x180052b90  mov     r8, r13; Size
0x180052b93  xor     edx, edx; Val
0x180052b95  mov     rcx, rbx; void *
0x180052b98  call    memset_0
0x180052b9d  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180052ba4  lea     rax, stru_18007E4D8
0x180052bab  test    r15d, r15d
0x180052bae  lea     rdx, asc_18007E4B8; "\"$"
0x180052bb5  mov     r9, rbx; KeyValueInformation
0x180052bb8  mov     r8d, 2; KeyValueInformationClass
0x180052bbe  cmovz   rdx, rax; ValueName
0x180052bc2  lea     rax, [rbp+1E0h+arg_0]
0x180052bc9  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180052bce  mov     [rsp+2E0h+Length], r13d; Length
0x180052bd3  call    cs:__imp_NtQueryValueKey
0x180052bd9  test    eax, eax
0x180052bdb  jns     short loc_180052BE7
0x180052bdd  mov     edi, 80070490h
0x180052be2  jmp     loc_180052E9A
0x180052be7  cmp     dword ptr [rbx+4], 1
0x180052beb  jnz     short loc_180052BDD
0x180052bed  lea     r13, [rsi+4]
0x180052bf1  mov     edx, 125h; unsigned __int64
0x180052bf6  lea     r14, [rbx+0Ch]
0x180052bfa  mov     rcx, r13; wchar_t *
0x180052bfd  mov     r8, r14; wchar_t *
0x180052c00  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180052c05  mov     edi, eax
0x180052c07  test    eax, eax
0x180052c09  jns     short loc_180052C39
0x180052c0b  mov     r9, gs:40h
0x180052c14  lea     r8, aWerCrashapiUUE_5; "WER/CrashAPI/%u:%u: ERROR Stringcchcopy"...
0x180052c1b  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180052c1f  xor     edx, edx; Level
0x180052c21  mov     ecx, 96h; ComponentId
0x180052c26  mov     [rsp+2E0h+Length], 1160h
0x180052c2e  call    cs:__imp_DbgPrintEx
0x180052c34  jmp     loc_180052E9A
0x180052c39  or      dword ptr [rsi], 1
0x180052c3c  mov     edi, 25Ah
0x180052c41  test    r15d, r15d
0x180052c44  jz      loc_180052D41
0x180052c4a  or      dword ptr [rsi], 7Ch
0x180052c4d  mov     r8d, edi; Size
0x180052c50  xor     edx, edx; Val
0x180052c52  mov     rcx, rbx; void *
0x180052c55  call    memset_0
0x180052c5a  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180052c61  lea     rax, [rbp+1E0h+arg_0]
0x180052c68  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180052c6d  lea     rdx, stru_18007E4C8; ValueName
0x180052c74  mov     r15d, 2
0x180052c7a  mov     [rsp+2E0h+Length], edi; Length
0x180052c7e  mov     r9, rbx; KeyValueInformation
0x180052c81  mov     r8d, r15d; KeyValueInformationClass
0x180052c84  call    cs:__imp_NtQueryValueKey
0x180052c8a  test    eax, eax
0x180052c8c  js      short loc_180052CA9
0x180052c8e  cmp     dword ptr [rbx+4], 4
0x180052c92  jnz     short loc_180052CA9
0x180052c94  mov     eax, [r14]
0x180052c97  neg     eax
0x180052c99  mov     eax, [rsi]
0x180052c9b  sbb     ecx, ecx
0x180052c9d  and     eax, 0FFFFFFFBh
0x180052ca0  not     ecx
0x180052ca2  and     ecx, 4
0x180052ca5  or      ecx, eax
0x180052ca7  mov     [rsi], ecx
0x180052ca9  test    byte ptr [rsi], 4
0x180052cac  jz      loc_180052D47
0x180052cb2  mov     r8, rdi; Size
0x180052cb5  xor     edx, edx; Val
0x180052cb7  mov     rcx, rbx; void *
0x180052cba  call    memset_0
0x180052cbf  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180052cc6  lea     rax, [rbp+1E0h+arg_0]
0x180052ccd  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180052cd2  lea     rdx, stru_18007E4E8; ValueName
0x180052cd9  mov     r9, rbx; KeyValueInformation
0x180052cdc  mov     [rsp+2E0h+Length], edi; Length
0x180052ce0  mov     r8d, r15d; KeyValueInformationClass
0x180052ce3  call    cs:__imp_NtQueryValueKey
0x180052ce9  test    eax, eax
0x180052ceb  js      short loc_180052D47
0x180052ced  cmp     dword ptr [rbx+4], 4
0x180052cf1  jnz     short loc_180052D47
0x180052cf3  mov     eax, [r14]
0x180052cf6  test    eax, eax
0x180052cf8  jz      short loc_180052D35
0x180052cfa  cmp     eax, 1
0x180052cfd  jz      short loc_180052D35
0x180052cff  cmp     eax, r15d
0x180052d02  jz      short loc_180052D35
0x180052d04  cmp     eax, 3
0x180052d07  jz      short loc_180052D35
0x180052d09  cmp     eax, 4
0x180052d0c  jz      short loc_180052D35
0x180052d0e  cmp     eax, 5
0x180052d11  jz      short loc_180052D35
0x180052d13  cmp     eax, 6
0x180052d16  jz      short loc_180052D35
0x180052d18  cmp     eax, 7
0x180052d1b  jz      short loc_180052D35
0x180052d1d  mov     ecx, [rsi]
0x180052d1f  cmp     eax, 80000000h
0x180052d24  jz      short loc_180052D2B
0x180052d26  or      ecx, 78h
0x180052d29  jmp     short loc_180052D31
0x180052d2b  and     ecx, 0FFFFFFF7h
0x180052d2e  or      ecx, 70h
0x180052d31  mov     [rsi], ecx
0x180052d33  jmp     short loc_180052D47
0x180052d35  shl     eax, 3
0x180052d38  xor     eax, [rsi]
0x180052d3a  and     eax, 78h
0x180052d3d  xor     [rsi], eax
0x180052d3f  jmp     short loc_180052D47
0x180052d41  mov     r15d, 2
0x180052d47  mov     r8, rdi; Size
0x180052d4a  xor     edx, edx; Val
0x180052d4c  mov     rcx, rbx; void *
0x180052d4f  call    memset_0
0x180052d54  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x180052d5b  lea     rax, [rbp+1E0h+arg_0]
0x180052d62  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x180052d67  lea     rdx, stru_18007E4A8; ValueName
0x180052d6e  mov     r9, rbx; KeyValueInformation
0x180052d71  mov     [rsp+2E0h+Length], edi; Length
0x180052d75  mov     r8d, r15d; KeyValueInformationClass
0x180052d78  call    cs:__imp_NtQueryValueKey
0x180052d7e  test    eax, eax
0x180052d80  js      short loc_180052DAC
0x180052d82  cmp     dword ptr [rbx+4], 1
0x180052d86  jnz     short loc_180052D8F
0x180052d88  cmp     word ptr [r14], 31h ; '1'
0x180052d8d  jz      short loc_180052D9B
0x180052d8f  cmp     dword ptr [rbx+4], 4
0x180052d93  jnz     short loc_180052DAC
0x180052d95  cmp     dword ptr [r14], 0
0x180052d99  jz      short loc_180052DAC
0x180052d9b  mov     rcx, r12; ProcessHandle
0x180052d9e  call    WerpIsProcessInAeDebugExclusionList
0x180052da3  test    eax, eax
0x180052da5  jnz     short loc_180052DAC
0x180052da7  mov     eax, r15d
0x180052daa  jmp     short loc_180052DAE
0x180052dac  xor     eax, eax
0x180052dae  and     dword ptr [rsi], 0FFFFFFFDh
0x180052db1  lea     r8, aWerCrashapiUUT_2; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052db8  or      [rsi], eax
0x180052dba  mov     ebx, 96h
0x180052dbf  mov     eax, [rsi]
0x180052dc1  mov     edx, r15d; Level
0x180052dc4  mov     r9, gs:40h
0x180052dcd  and     eax, 1
0x180052dd0  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180052dd4  mov     ecx, ebx; ComponentId
0x180052dd6  mov     [rsp+2E0h+Length], 11C5h
0x180052dde  call    cs:__imp_DbgPrintEx
0x180052de4  mov     eax, [rsi]
0x180052de6  lea     r8, aWerCrashapiUUT_5; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052ded  mov     r9, gs:40h
0x180052df6  mov     edx, r15d; Level
0x180052df9  shr     eax, 1
0x180052dfb  mov     ecx, ebx; ComponentId
0x180052dfd  and     eax, 1
0x180052e00  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180052e04  mov     [rsp+2E0h+Length], 11C6h
0x180052e0c  call    cs:__imp_DbgPrintEx
0x180052e12  mov     eax, [rsi]
0x180052e14  lea     r8, aWerCrashapiUUT_1; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052e1b  mov     r9, gs:40h
0x180052e24  mov     edx, r15d; Level
0x180052e27  shr     eax, 2
0x180052e2a  mov     ecx, ebx; ComponentId
0x180052e2c  and     eax, 1
0x180052e2f  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180052e33  mov     [rsp+2E0h+Length], 11C7h
0x180052e3b  call    cs:__imp_DbgPrintEx
0x180052e41  mov     eax, [rsi]
0x180052e43  lea     r8, aWerCrashapiUUT_3; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052e4a  mov     r9, gs:40h
0x180052e53  mov     edx, r15d; Level
0x180052e56  shr     eax, 3
0x180052e59  mov     ecx, ebx; ComponentId
0x180052e5b  and     eax, 0Fh
0x180052e5e  mov     dword ptr [rsp+2E0h+ResultLength], eax
0x180052e62  mov     [rsp+2E0h+Length], 11C8h
0x180052e6a  call    cs:__imp_DbgPrintEx
0x180052e70  mov     r9, gs:40h
0x180052e79  lea     r8, aWerCrashapiUUT_4; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x180052e80  mov     edx, r15d; Level
0x180052e83  mov     [rsp+2E0h+ResultLength], r13
0x180052e88  mov     ecx, ebx; ComponentId
0x180052e8a  mov     [rsp+2E0h+Length], 11C9h
0x180052e92  call    cs:__imp_DbgPrintEx
0x180052e98  xor     edi, edi
0x180052e9a  lea     rcx, [rbp+1E0h+arg_18]
0x180052ea1  call    ??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$generic_delete@U_PROC_THREAD_ATTRIBUTE_LIST@@Uvirtualfree_release@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,tlx::generic_delete<_PROC_THREAD_ATTRIBUTE_LIST,virtualfree_release>>(void)
0x180052ea6  lea     rcx, [rbp+1E0h+KeyHandle]
0x180052ead  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180052eb2  mov     eax, edi
  ... truncated ...
```
