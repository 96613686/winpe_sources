# WerpGetDebugger

- ea: `0x18001c370`
- end: `0x18001c874`
- name: `WerpGetDebugger`
- size: `1284`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014c34`

## callees

- `0x180003474`
- `0x180003617`
- `0x180007704`
- `0x18001bfb0`
- `0x18001c370`
- `0x18001cb90`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18001c539`
- `ntdll!NtQueryValueKey` at `0x18001c62b`
- `ntdll!NtQueryValueKey` at `0x18001c686`
- `ntdll!NtQueryValueKey` at `0x18001c6fe`
- `ntdll!NtQueryValueKey` at `0x18001c539`
- `ntdll!NtQueryValueKey` at `0x18001c62b`
- `ntdll!NtQueryValueKey` at `0x18001c686`
- `ntdll!NtQueryValueKey` at `0x18001c6fe`
- `ntdll!NtOpenKey` at `0x18001c4e1`
- `ntdll!NtOpenKey` at `0x18001c4e1`
- `ntdll!DbgPrintEx` at `0x18001c5d5`
- `ntdll!DbgPrintEx` at `0x18001c765`
- `ntdll!DbgPrintEx` at `0x18001c793`
- `ntdll!DbgPrintEx` at `0x18001c7c2`
- `ntdll!DbgPrintEx` at `0x18001c7f1`
- `ntdll!DbgPrintEx` at `0x18001c819`
- `ntdll!DbgPrintEx` at `0x18001c5d5`
- `ntdll!DbgPrintEx` at `0x18001c765`
- `ntdll!DbgPrintEx` at `0x18001c793`
- `ntdll!DbgPrintEx` at `0x18001c7c2`
- `ntdll!DbgPrintEx` at `0x18001c7f1`
- `ntdll!DbgPrintEx` at `0x18001c819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c84a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c84a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c473`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18001c473`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001c82c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18001c82c`

## string_xrefs

- `0x18001c5bf`: `WER/CrashAPI/%u:%u: ERROR Stringcchcopy failed while copying the debugger path 0x%x\n`

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
  int IsProtectedProcess; // r15d
  struct _UNICODE_STRING *v20; // rcx
  void **v21; // rax
  NTSTATUS v22; // edi
  unsigned int v23; // edi
  struct _UNICODE_STRING *v24; // rdx
  __int64 v25; // rax
  int *v26; // r14
  _WORD *v27; // r8
  _WORD *v28; // rcx
  __int64 v29; // rdx
  _WORD *v30; // rcx
  DWORD v31; // eax
  int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // eax
  unsigned int v36; // edi
  DWORD CurrentProcessId_0; // eax
  int v38; // edi
  DWORD v39; // eax
  int v40; // edi
  DWORD v41; // eax
  int v42; // edi
  DWORD v43; // eax
  DWORD v44; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v47[640]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ResultLength; // [rsp+2F0h] [rbp+1F0h] BYREF
  HANDLE KeyHandle; // [rsp+300h] [rbp+200h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !ProcessHandle || !a2 )
    return 2147942487LL;
  memset_0(v47, 0, 0x250u);
  v4 = a2;
  v5 = v47;
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
  v18 = (int *)VirtualAlloc(0, 0x25Au, 0x1000u, 4u);
  if ( v18 )
  {
    IsProtectedProcess = WerpIsProtectedProcess(ProcessHandle);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    v20 = (struct _UNICODE_STRING *)&unk_18004D918;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( !IsProtectedProcess )
      v20 = (struct _UNICODE_STRING *)&unk_18004D928;
    ObjectAttributes.ObjectName = v20;
    v21 = (void **)tlx::replace<tlx::file_handle_traits>(&KeyHandle);
    v22 = NtOpenKey(v21, 1u, &ObjectAttributes);
    if ( v22 >= 0 )
    {
      memset_0(v18, 0, 0x25Au);
      v24 = (struct _UNICODE_STRING *)L"\"$";
      if ( !IsProtectedProcess )
        v24 = (struct _UNICODE_STRING *)&stru_18004D8D8;
      if ( NtQueryValueKey(KeyHandle, v24, KeyValuePartialInformation, v18, 0x25Au, &ResultLength) >= 0 && v18[1] == 1 )
      {
        v25 = 2147483646;
        v26 = v18 + 3;
        v27 = a2 + 1;
        v28 = v18 + 3;
        v29 = 293;
        do
        {
          if ( !v25 )
            break;
          if ( !*v28 )
            break;
          *v27++ = *v28++;
          --v25;
          --v29;
        }
        while ( v29 );
        v30 = v27 - 1;
        v23 = v29 == 0 ? 0x8007007A : 0;
        if ( v29 )
          v30 = v27;
        *v30 = 0;
        if ( v29 )
        {
          *a2 |= 1u;
          if ( IsProtectedProcess )
          {
            *a2 |= 0x7Cu;
            memset_0(v18, 0, 0x25Au);
            if ( NtQueryValueKey(
                   KeyHandle,
                   (PUNICODE_STRING)&stru_18004D8B8,
                   KeyValuePartialInformation,
                   v18,
                   0x25Au,
                   &ResultLength) >= 0
              && v18[1] == 4 )
            {
              *a2 = *a2 & 0xFFFFFFFB | (*v26 == 0 ? 4 : 0);
            }
            if ( (*(_BYTE *)a2 & 4) != 0 )
            {
              memset_0(v18, 0, 0x25Au);
              if ( NtQueryValueKey(
                     KeyHandle,
                     (PUNICODE_STRING)&stru_18004D908,
                     KeyValuePartialInformation,
                     v18,
                     0x25Au,
                     &ResultLength) >= 0
                && v18[1] == 4 )
              {
                v32 = *v26;
                if ( (unsigned int)*v26 < 8 )
                {
                  *a2 ^= (*a2 ^ (8 * v32)) & 0x78;
                }
                else
                {
                  v33 = *a2;
                  if ( v32 == 0x80000000 )
                    v34 = v33 & 0xFFFFFF87 | 0x70;
                  else
                    v34 = v33 | 0x78;
                  *a2 = v34;
                }
              }
            }
          }
          memset_0(v18, 0, 0x25Au);
          if ( NtQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&stru_18004D8A8,
                 KeyValuePartialInformation,
                 v18,
                 0x25Au,
                 &ResultLength) >= 0
            && (v18[1] == 1 && *(_WORD *)v26 == 49 || v18[1] == 4 && *v26)
            && !(unsigned int)WerpIsProcessInAeDebugExclusionList(ProcessHandle) )
          {
            v35 = 2;
          }
          else
          {
            v35 = 0;
          }
          *a2 &= ~2u;
          *a2 |= v35;
          v36 = *a2;
          CurrentProcessId_0 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            2u,
            "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.Available: %u\n",
            CurrentProcessId_0,
            4549,
            v36 & 1);
          v38 = (*a2 >> 1) & 1;
          v39 = GetCurrentProcessId_0();
          DbgPrintEx(0x96u, 2u, "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.AutoEnabled: %u\n", v39, 4550, v38);
          v40 = (*a2 >> 2) & 1;
          v41 = GetCurrentProcessId_0();
          DbgPrintEx(0x96u, 2u, "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.Protected: %u\n", v41, 4551, v40);
          v42 = (*a2 >> 3) & 0xF;
          v43 = GetCurrentProcessId_0();
          DbgPrintEx(0x96u, 2u, "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.ProtectionLevel: %08X\n", v43, 4552, v42);
          v44 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            2u,
            "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER_INFO.Debugger: %S\n",
            v44,
            4553,
            (const wchar_t *)a2 + 2);
          v23 = 0;
        }
        else
        {
          v31 = GetCurrentProcessId_0();
          DbgPrintEx(
            0x96u,
            0,
            "WER/CrashAPI/%u:%u: ERROR Stringcchcopy failed while copying the debugger path 0x%x\n",
            v31,
            4448,
            v23);
        }
      }
      else
      {
        v23 = -2147023728;
      }
    }
    else
    {
      v23 = v22 | 0x10000000;
    }
    VirtualFree(v18, 0, 0x8000u);
  }
  else
  {
    v23 = -2147024882;
  }
  if ( (unsigned __int64)KeyHandle + 1 > 1 )
    CloseHandle(KeyHandle);
  return v23;
}

```

## disassembly

```asm
0x18001c370  mov     [rsp-8+arg_8], rbx
0x18001c375  push    rbp
0x18001c376  push    rsi
0x18001c377  push    rdi
0x18001c378  push    r12
0x18001c37a  push    r13
0x18001c37c  push    r14
0x18001c37e  push    r15
0x18001c380  lea     rbp, [rsp-1B0h]
0x18001c388  sub     rsp, 2B0h
0x18001c38f  xor     r14d, r14d
0x18001c392  xorps   xmm0, xmm0
0x18001c395  mov     [rbp+1E0h+KeyHandle], r14
0x18001c39c  mov     rsi, rdx
0x18001c39f  mov     [rbp+1E0h+arg_0], r14d
0x18001c3a6  mov     r12, rcx
0x18001c3a9  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.Length], xmm0
0x18001c3ae  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.ObjectName], xmm0
0x18001c3b3  movups  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001c3b8  test    rcx, rcx
0x18001c3bb  jz      loc_18001C854
0x18001c3c1  test    rdx, rdx
0x18001c3c4  jz      loc_18001C854
0x18001c3ca  xor     edx, edx; Val
0x18001c3cc  lea     rcx, [rsp+2E0h+var_280]; void *
0x18001c3d1  mov     r8d, 250h; Size
0x18001c3d7  call    memset_0
0x18001c3dc  lea     r8d, [r14+4]
0x18001c3e0  mov     rax, rsi
0x18001c3e3  lea     rcx, [rsp+2E0h+var_280]
0x18001c3e8  mov     edx, r8d
0x18001c3eb  lea     r9d, [r8+7Ch]
0x18001c3ef  movups  xmm0, xmmword ptr [rcx]
0x18001c3f2  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c3f6  movups  xmmword ptr [rax], xmm0
0x18001c3f9  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c3fd  movups  xmmword ptr [rax+10h], xmm1
0x18001c401  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c405  movups  xmmword ptr [rax+20h], xmm0
0x18001c409  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c40d  movups  xmmword ptr [rax+30h], xmm1
0x18001c411  movups  xmm1, xmmword ptr [rcx+50h]
0x18001c415  movups  xmmword ptr [rax+40h], xmm0
0x18001c419  movups  xmm0, xmmword ptr [rcx+60h]
0x18001c41d  movups  xmmword ptr [rax+50h], xmm1
0x18001c421  movups  xmm1, xmmword ptr [rcx+70h]
0x18001c425  add     rcx, r9
0x18001c428  movups  xmmword ptr [rax+60h], xmm0
0x18001c42c  movups  xmmword ptr [rax+70h], xmm1
0x18001c430  add     rax, r9
0x18001c433  sub     rdx, 1
0x18001c437  jnz     short loc_18001C3EF
0x18001c439  movups  xmm0, xmmword ptr [rcx]
0x18001c43c  mov     r9d, r8d; flProtect
0x18001c43f  mov     r13d, 25Ah
0x18001c445  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c449  mov     r8d, 1000h; flAllocationType
0x18001c44f  mov     edx, r13d; dwSize
0x18001c452  movups  xmmword ptr [rax], xmm0
0x18001c455  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c459  movups  xmmword ptr [rax+10h], xmm1
0x18001c45d  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c461  movups  xmmword ptr [rax+20h], xmm0
0x18001c465  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c469  xor     ecx, ecx; lpAddress
0x18001c46b  movups  xmmword ptr [rax+30h], xmm1
0x18001c46f  movups  xmmword ptr [rax+40h], xmm0
0x18001c473  call    cs:__imp_VirtualAlloc
0x18001c479  mov     rbx, rax
0x18001c47c  test    rax, rax
0x18001c47f  jz      loc_18001C834
0x18001c485  mov     rcx, r12; ProcessHandle
0x18001c488  call    ?WerpIsProtectedProcess@@YAHPEAX@Z; WerpIsProtectedProcess(void *)
0x18001c48d  mov     r15d, eax
0x18001c490  mov     [rsp+2E0h+ObjectAttributes.Length], 30h ; '0'
0x18001c498  lea     rax, unk_18004D928
0x18001c49f  mov     [rsp+2E0h+ObjectAttributes.RootDirectory], r14
0x18001c4a4  xorps   xmm0, xmm0
0x18001c4a7  mov     [rsp+2E0h+ObjectAttributes.Attributes], 40h ; '@'
0x18001c4af  test    r15d, r15d
0x18001c4b2  lea     rcx, unk_18004D918
0x18001c4b9  movdqu  xmmword ptr [rsp+2E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001c4bf  cmovz   rcx, rax
0x18001c4c3  mov     [rsp+2E0h+ObjectAttributes.ObjectName], rcx
0x18001c4c8  lea     rcx, [rbp+1E0h+KeyHandle]
0x18001c4cf  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18001c4d4  mov     rcx, rax; KeyHandle
0x18001c4d7  lea     r8, [rsp+2E0h+ObjectAttributes]; ObjectAttributes
0x18001c4dc  mov     edx, 1; DesiredAccess
0x18001c4e1  call    cs:__imp_NtOpenKey
0x18001c4e7  mov     edi, eax
0x18001c4e9  test    eax, eax
0x18001c4eb  jns     short loc_18001C4F6
0x18001c4ed  bts     edi, 1Ch
0x18001c4f1  jmp     loc_18001C821
0x18001c4f6  mov     r8, r13; Size
0x18001c4f9  xor     edx, edx; Val
0x18001c4fb  mov     rcx, rbx; void *
0x18001c4fe  call    memset_0
0x18001c503  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x18001c50a  lea     rax, stru_18004D8D8
0x18001c511  test    r15d, r15d
0x18001c514  lea     rdx, asc_18004D8C8; "\"$"
0x18001c51b  mov     r9, rbx; KeyValueInformation
0x18001c51e  mov     r8d, 2; KeyValueInformationClass
0x18001c524  cmovz   rdx, rax; ValueName
0x18001c528  lea     rax, [rbp+1E0h+arg_0]
0x18001c52f  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18001c534  mov     [rsp+2E0h+Length], r13d; Length
0x18001c539  call    cs:__imp_NtQueryValueKey
0x18001c53f  test    eax, eax
0x18001c541  jns     short loc_18001C54D
0x18001c543  mov     edi, 80070490h
0x18001c548  jmp     loc_18001C821
0x18001c54d  cmp     dword ptr [rbx+4], 1
0x18001c551  jnz     short loc_18001C543
0x18001c553  lea     r13, [rsi+4]
0x18001c557  mov     eax, 7FFFFFFEh
0x18001c55c  lea     r14, [rbx+0Ch]
0x18001c560  mov     r8, r13
0x18001c563  mov     rcx, r14
0x18001c566  mov     edx, 125h
0x18001c56b  xor     r10d, r10d
0x18001c56e  test    rax, rax
0x18001c571  jz      short loc_18001C592
0x18001c573  movzx   r9d, word ptr [rcx]
0x18001c577  test    r9w, r9w
0x18001c57b  jz      short loc_18001C592
0x18001c57d  mov     [r8], r9w
0x18001c581  add     rcx, 2
0x18001c585  add     r8, 2
0x18001c589  dec     rax
0x18001c58c  sub     rdx, 1
0x18001c590  jnz     short loc_18001C56E
0x18001c592  mov     rax, rdx
0x18001c595  lea     rcx, [r8-2]
0x18001c599  neg     rax
0x18001c59c  sbb     edi, edi
0x18001c59e  not     edi
0x18001c5a0  and     edi, 8007007Ah
0x18001c5a6  test    rdx, rdx
0x18001c5a9  cmovnz  rcx, r8
0x18001c5ad  mov     [rcx], r10w
0x18001c5b1  jnz     short loc_18001C5E0
0x18001c5b3  call    GetCurrentProcessId_0
0x18001c5b8  mov     r9d, eax
0x18001c5bb  mov     dword ptr [rsp+2E0h+ResultLength], edi
0x18001c5bf  lea     r8, aWerCrashapiUUE_2; "WER/CrashAPI/%u:%u: ERROR Stringcchcopy"...
0x18001c5c6  mov     [rsp+2E0h+Length], 1160h
0x18001c5ce  xor     edx, edx; Level
0x18001c5d0  mov     ecx, 96h; ComponentId
0x18001c5d5  call    cs:__imp_DbgPrintEx
0x18001c5db  jmp     loc_18001C821
0x18001c5e0  or      dword ptr [rsi], 1
0x18001c5e3  mov     edi, 25Ah
0x18001c5e8  test    r15d, r15d
0x18001c5eb  jz      loc_18001C6C7
0x18001c5f1  or      dword ptr [rsi], 7Ch
0x18001c5f4  mov     r8d, edi; Size
0x18001c5f7  xor     edx, edx; Val
0x18001c5f9  mov     rcx, rbx; void *
0x18001c5fc  call    memset_0
0x18001c601  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x18001c608  lea     rax, [rbp+1E0h+arg_0]
0x18001c60f  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18001c614  lea     rdx, stru_18004D8B8; ValueName
0x18001c61b  mov     r15d, 2
0x18001c621  mov     [rsp+2E0h+Length], edi; Length
0x18001c625  mov     r9, rbx; KeyValueInformation
0x18001c628  mov     r8d, r15d; KeyValueInformationClass
0x18001c62b  call    cs:__imp_NtQueryValueKey
0x18001c631  test    eax, eax
0x18001c633  js      short loc_18001C650
0x18001c635  cmp     dword ptr [rbx+4], 4
0x18001c639  jnz     short loc_18001C650
0x18001c63b  mov     eax, [r14]
0x18001c63e  neg     eax
0x18001c640  mov     eax, [rsi]
0x18001c642  sbb     ecx, ecx
0x18001c644  and     eax, 0FFFFFFFBh
0x18001c647  not     ecx
0x18001c649  and     ecx, 4
0x18001c64c  or      ecx, eax
0x18001c64e  mov     [rsi], ecx
0x18001c650  test    byte ptr [rsi], 4
0x18001c653  jz      short loc_18001C6CD
0x18001c655  mov     r8, rdi; Size
0x18001c658  xor     edx, edx; Val
0x18001c65a  mov     rcx, rbx; void *
0x18001c65d  call    memset_0
0x18001c662  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x18001c669  lea     rax, [rbp+1E0h+arg_0]
0x18001c670  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18001c675  lea     rdx, stru_18004D908; ValueName
0x18001c67c  mov     r9, rbx; KeyValueInformation
0x18001c67f  mov     [rsp+2E0h+Length], edi; Length
0x18001c683  mov     r8d, r15d; KeyValueInformationClass
0x18001c686  call    cs:__imp_NtQueryValueKey
0x18001c68c  test    eax, eax
0x18001c68e  js      short loc_18001C6CD
0x18001c690  cmp     dword ptr [rbx+4], 4
0x18001c694  jnz     short loc_18001C6CD
0x18001c696  mov     ecx, [r14]
0x18001c699  cmp     ecx, 8
0x18001c69c  jb      short loc_18001C6B7
0x18001c69e  mov     eax, [rsi]
0x18001c6a0  cmp     ecx, 80000000h
0x18001c6a6  jz      short loc_18001C6AD
0x18001c6a8  or      eax, 78h
0x18001c6ab  jmp     short loc_18001C6B3
0x18001c6ad  and     eax, 0FFFFFFF7h
0x18001c6b0  or      eax, 70h
0x18001c6b3  mov     [rsi], eax
0x18001c6b5  jmp     short loc_18001C6CD
0x18001c6b7  lea     eax, ds:0[rcx*8]
0x18001c6be  xor     eax, [rsi]
0x18001c6c0  and     eax, 78h
0x18001c6c3  xor     [rsi], eax
0x18001c6c5  jmp     short loc_18001C6CD
0x18001c6c7  mov     r15d, 2
0x18001c6cd  mov     r8, rdi; Size
0x18001c6d0  xor     edx, edx; Val
0x18001c6d2  mov     rcx, rbx; void *
0x18001c6d5  call    memset_0
0x18001c6da  mov     rcx, [rbp+1E0h+KeyHandle]; KeyHandle
0x18001c6e1  lea     rax, [rbp+1E0h+arg_0]
0x18001c6e8  mov     [rsp+2E0h+ResultLength], rax; ResultLength
0x18001c6ed  lea     rdx, stru_18004D8A8; ValueName
0x18001c6f4  mov     r9, rbx; KeyValueInformation
0x18001c6f7  mov     [rsp+2E0h+Length], edi; Length
0x18001c6fb  mov     r8d, r15d; KeyValueInformationClass
0x18001c6fe  call    cs:__imp_NtQueryValueKey
0x18001c704  test    eax, eax
0x18001c706  js      short loc_18001C732
0x18001c708  cmp     dword ptr [rbx+4], 1
0x18001c70c  jnz     short loc_18001C715
0x18001c70e  cmp     word ptr [r14], 31h ; '1'
0x18001c713  jz      short loc_18001C721
0x18001c715  cmp     dword ptr [rbx+4], 4
0x18001c719  jnz     short loc_18001C732
0x18001c71b  cmp     dword ptr [r14], 0
0x18001c71f  jz      short loc_18001C732
0x18001c721  mov     rcx, r12; ProcessHandle
0x18001c724  call    WerpIsProcessInAeDebugExclusionList
0x18001c729  test    eax, eax
0x18001c72b  jnz     short loc_18001C732
0x18001c72d  mov     eax, r15d
0x18001c730  jmp     short loc_18001C734
0x18001c732  xor     eax, eax
0x18001c734  and     dword ptr [rsi], 0FFFFFFFDh
0x18001c737  or      [rsi], eax
0x18001c739  mov     edi, [rsi]
0x18001c73b  call    GetCurrentProcessId_0
0x18001c740  and     edi, 1
0x18001c743  lea     r8, aWerCrashapiUUT_2; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x18001c74a  mov     r14d, 96h
0x18001c750  mov     dword ptr [rsp+2E0h+ResultLength], edi
0x18001c754  mov     ecx, r14d; ComponentId
0x18001c757  mov     [rsp+2E0h+Length], 11C5h
0x18001c75f  mov     r9d, eax
0x18001c762  mov     edx, r15d; Level
0x18001c765  call    cs:__imp_DbgPrintEx
0x18001c76b  mov     edi, [rsi]
0x18001c76d  shr     edi, 1
0x18001c76f  and     edi, 1
0x18001c772  call    GetCurrentProcessId_0
0x18001c777  mov     r9d, eax
0x18001c77a  mov     dword ptr [rsp+2E0h+ResultLength], edi
0x18001c77e  lea     r8, aWerCrashapiUUT_5; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x18001c785  mov     [rsp+2E0h+Length], 11C6h
0x18001c78d  mov     edx, r15d; Level
0x18001c790  mov     ecx, r14d; ComponentId
0x18001c793  call    cs:__imp_DbgPrintEx
0x18001c799  mov     edi, [rsi]
0x18001c79b  shr     edi, 2
0x18001c79e  and     edi, 1
0x18001c7a1  call    GetCurrentProcessId_0
0x18001c7a6  mov     r9d, eax
0x18001c7a9  mov     dword ptr [rsp+2E0h+ResultLength], edi
0x18001c7ad  lea     r8, aWerCrashapiUUT_1; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x18001c7b4  mov     [rsp+2E0h+Length], 11C7h
0x18001c7bc  mov     edx, r15d; Level
0x18001c7bf  mov     ecx, r14d; ComponentId
0x18001c7c2  call    cs:__imp_DbgPrintEx
0x18001c7c8  mov     edi, [rsi]
0x18001c7ca  shr     edi, 3
0x18001c7cd  and     edi, 0Fh
0x18001c7d0  call    GetCurrentProcessId_0
0x18001c7d5  mov     r9d, eax
0x18001c7d8  mov     dword ptr [rsp+2E0h+ResultLength], edi
0x18001c7dc  lea     r8, aWerCrashapiUUT_3; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x18001c7e3  mov     [rsp+2E0h+Length], 11C8h
0x18001c7eb  mov     edx, r15d; Level
0x18001c7ee  mov     ecx, r14d; ComponentId
0x18001c7f1  call    cs:__imp_DbgPrintEx
0x18001c7f7  call    GetCurrentProcessId_0
0x18001c7fc  mov     r9d, eax
0x18001c7ff  mov     [rsp+2E0h+ResultLength], r13
0x18001c804  lea     r8, aWerCrashapiUUT_4; "WER/CrashAPI/%u:%u: TRACE WERP_DEBUGGER"...
0x18001c80b  mov     [rsp+2E0h+Length], 11C9h
  ... truncated ...
```
