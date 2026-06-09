# VerifyTrust(HWND__ *,_GUID,ushort *,void *,ushort *,ushort *,ulong,ulong,void *)

- ea: `0x14000c0fc`
- end: `0x14000c384`
- name: `?VerifyTrust@@YAJPEAUHWND__@@U_GUID@@PEAGPEAX22KK3@Z`
- size: `648`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct _GUID *@<rdx>, unsigned __int16 *@<r8>, void *@<r9>, LPCWSTR lpFileName, unsigned __int16 *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14000747c`

## callees

- `0x140001af3`
- `0x140009d84`
- `0x14000c02c`
- `0x14000c0fc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000c361`
- `KERNEL32!CloseHandle` at `0x14000c361`
- `KERNEL32!GetCurrentProcess` at `0x14000c15d`
- `KERNEL32!GetCurrentProcess` at `0x14000c16c`
- `KERNEL32!GetCurrentProcess` at `0x14000c15d`
- `KERNEL32!GetCurrentProcess` at `0x14000c16c`
- `KERNEL32!DuplicateHandle` at `0x14000c19e`
- `KERNEL32!DuplicateHandle` at `0x14000c19e`
- `KERNEL32!CreateFileW` at `0x14000c1d9`
- `KERNEL32!CreateFileW` at `0x14000c1d9`
- `KERNEL32!GetLastError` at `0x14000c326`
- `KERNEL32!GetLastError` at `0x14000c326`
- `iertutil!__imp_GetValue` at `0x14000c2b3`
- `iertutil!__imp_GetValue` at `0x14000c2b3`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x14000c27a`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x14000c27a`

## pseudocode

```c
__int64 __fastcall VerifyTrust(
        HWND a1,
        struct _GUID *a2,
        unsigned __int16 *a3,
        char *a4,
        LPCWSTR lpFileName,
        unsigned __int16 *a6,
        DWORD a7,
        DWORD a8,
        void *a9)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v15; // rax
  HANDLE FileW; // rbx
  int v17; // ebx
  int v18; // ebx
  signed int LastError; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-C0h] BYREF
  void *v21; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp-B0h] BYREF
  _WINTRUST_DATA v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v25; // [rsp+D8h] [rbp-28h]
  unsigned __int16 *FileNameFromPath; // [rsp+E0h] [rbp-20h]
  LPCWSTR v27; // [rsp+E8h] [rbp-18h]
  HANDLE v28; // [rsp+F0h] [rbp-10h]

  v21 = a9;
  TargetHandle = (HANDLE)-1LL;
  if ( !lpFileName )
    return 2147942487LL;
  if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    TargetHandle = FileW;
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v15 = GetCurrentProcess();
    DuplicateHandle(v15, a4, CurrentProcess, &TargetHandle, 0, 0, 2u);
    FileW = TargetHandle;
  }
  if ( !FileW || FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    memset_0(&v24, 0, 0x48u);
    v22[0] = 32;
    v22[3] = 0;
    memset_0(&v23, 0, 0x58u);
    v23.dwUIChoice = a7;
    v23.dwUIContext = a8;
    v23.pPolicyCallbackData = v21;
    v22[1] = a3;
    v22[2] = FileW;
    v17 = 1;
    v23.pFile = (struct WINTRUST_FILE_INFO_ *)v22;
    v23.cbStruct = 88;
    v23.dwUnionChoice = 1;
    if ( (unsigned int)IsPolicyEnabledValue((__int64 *)SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4) )
    {
      LODWORD(v21) = 0;
      if ( (int)GetValue(
                  (__int64 *)SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4,
                  0,
                  1,
                  &v21,
                  4,
                  0,
                  0) >= 0 )
        v17 = (_DWORD)v21 == 0;
    }
    v23.dwProvFlags = (v17 << 13) | 0x4000;
    if ( a6 )
    {
      FileNameFromPath = FindFileNameFromPath(lpFileName);
      v23.dwUnionChoice = 2;
      v23.dwUIChoice = 2;
      v23.pFile = (struct WINTRUST_FILE_INFO_ *)&v24;
      v24 = 72;
      v25 = a6;
      v27 = lpFileName;
      v28 = TargetHandle;
    }
    v18 = SpinCallWinVerityTrust(a1, a2, &v23);
  }
  if ( v18 >= 1 )
    v18 = -2146762485;
  if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TargetHandle);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14000c0fc  push    rbp
0x14000c0fe  push    rbx
0x14000c0ff  push    rsi
0x14000c100  push    rdi
0x14000c101  push    r12
0x14000c103  push    r13
0x14000c105  push    r14
0x14000c107  push    r15
0x14000c109  lea     rbp, [rsp-28h]
0x14000c10e  sub     rsp, 128h
0x14000c115  mov     rdi, [rbp+60h+lpFileName]
0x14000c11c  mov     rsi, r9
0x14000c11f  mov     rax, [rbp+60h+arg_40]
0x14000c126  mov     r13, r8
0x14000c129  mov     r14, [rbp+60h+arg_28]
0x14000c130  mov     r12, rdx
0x14000c133  mov     [rsp+160h+var_118], rax
0x14000c138  mov     r15, rcx
0x14000c13b  mov     [rsp+160h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x14000c144  test    rdi, rdi
0x14000c147  jnz     short loc_14000C153
0x14000c149  mov     eax, 80070057h
0x14000c14e  jmp     loc_14000C36F
0x14000c153  lea     rax, [r9-1]
0x14000c157  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c15b  ja      short loc_14000C1B1
0x14000c15d  call    cs:__imp_GetCurrentProcess
0x14000c164  nop     dword ptr [rax+rax+00h]
0x14000c169  mov     rbx, rax
0x14000c16c  call    cs:__imp_GetCurrentProcess
0x14000c173  nop     dword ptr [rax+rax+00h]
0x14000c178  mov     [rsp+160h+dwOptions], 2; dwOptions
0x14000c180  lea     r9, [rsp+160h+TargetHandle]; lpTargetHandle
0x14000c185  mov     rcx, rax; hSourceProcessHandle
0x14000c188  mov     [rsp+160h+bInheritHandle], 0; bInheritHandle
0x14000c190  mov     r8, rbx; hTargetProcessHandle
0x14000c193  mov     [rsp+160h+dwDesiredAccess], 0; dwDesiredAccess
0x14000c19b  mov     rdx, rsi; hSourceHandle
0x14000c19e  call    cs:__imp_DuplicateHandle
0x14000c1a5  nop     dword ptr [rax+rax+00h]
0x14000c1aa  mov     rbx, [rsp+160h+TargetHandle]
0x14000c1af  jmp     short loc_14000C1ED
0x14000c1b1  xor     r9d, r9d; lpSecurityAttributes
0x14000c1b4  mov     qword ptr [rsp+160h+dwOptions], 0; hTemplateFile
0x14000c1bd  mov     [rsp+160h+bInheritHandle], 80h; dwFlagsAndAttributes
0x14000c1c5  mov     edx, 80000000h; dwDesiredAccess
0x14000c1ca  mov     rcx, rdi; lpFileName
0x14000c1cd  mov     [rsp+160h+dwDesiredAccess], 3; dwCreationDisposition
0x14000c1d5  lea     r8d, [r9+1]; dwShareMode
0x14000c1d9  call    cs:__imp_CreateFileW
0x14000c1e0  nop     dword ptr [rax+rax+00h]
0x14000c1e5  mov     rbx, rax
0x14000c1e8  mov     [rsp+160h+TargetHandle], rax
0x14000c1ed  test    rbx, rbx
0x14000c1f0  jz      loc_14000C326
0x14000c1f6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000c1fa  jz      loc_14000C326
0x14000c200  xor     edx, edx; Val
0x14000c202  lea     rcx, [rbp+60h+var_90]; void *
0x14000c206  lea     r8d, [rdx+48h]; Size
0x14000c20a  call    memset_0
0x14000c20f  mov     esi, 58h ; 'X'
0x14000c214  mov     [rsp+160h+var_110], 20h ; ' '
0x14000c21d  mov     r8d, esi; Size
0x14000c220  mov     [rsp+160h+var_F8], 0
0x14000c229  xor     edx, edx; Val
0x14000c22b  lea     rcx, [rsp+160h+var_F0]; void *
0x14000c230  call    memset_0
0x14000c235  mov     eax, [rbp+60h+arg_30]
0x14000c23b  mov     rcx, cs:?IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4
0x14000c242  mov     [rbp+60h+var_F0.dwUIChoice], eax
0x14000c245  mov     eax, [rbp+60h+arg_38]
0x14000c24b  mov     [rbp+60h+var_F0.dwUIContext], eax
0x14000c24e  mov     rax, [rsp+160h+var_118]
0x14000c253  mov     [rsp+160h+var_F0.pPolicyCallbackData], rax
0x14000c258  lea     rax, [rsp+160h+var_110]
0x14000c25d  mov     [rsp+160h+var_108], r13
0x14000c262  lea     r13d, [rsi-57h]
0x14000c266  mov     [rsp+160h+var_100], rbx
0x14000c26b  mov     ebx, r13d
0x14000c26e  mov     qword ptr [rbp+60h+var_F0.28h], rax
0x14000c272  mov     [rsp+160h+var_F0.cbStruct], esi
0x14000c276  mov     [rbp+60h+var_F0.dwUnionChoice], r13d
0x14000c27a  call    cs:__imp_IsPolicyEnabledValue
0x14000c281  nop     dword ptr [rax+rax+00h]
0x14000c286  xor     esi, esi
0x14000c288  test    eax, eax
0x14000c28a  jz      short loc_14000C2CC
0x14000c28c  mov     rcx, cs:?IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4
0x14000c293  lea     r9, [rsp+160h+var_118]
0x14000c298  mov     qword ptr [rsp+160h+dwOptions], rsi
0x14000c29d  mov     r8d, r13d
0x14000c2a0  mov     qword ptr [rsp+160h+bInheritHandle], rsi
0x14000c2a5  xor     edx, edx
0x14000c2a7  mov     [rsp+160h+dwDesiredAccess], 4
0x14000c2af  mov     dword ptr [rsp+160h+var_118], esi
0x14000c2b3  call    cs:__imp_GetValue
0x14000c2ba  nop     dword ptr [rax+rax+00h]
0x14000c2bf  test    eax, eax
0x14000c2c1  js      short loc_14000C2CC
0x14000c2c3  cmp     dword ptr [rsp+160h+var_118], esi
0x14000c2c7  mov     ebx, esi
0x14000c2c9  setz    bl
0x14000c2cc  shl     ebx, 0Dh
0x14000c2cf  bts     ebx, 0Eh
0x14000c2d3  mov     [rbp+60h+var_F0.dwProvFlags], ebx
0x14000c2d6  test    r14, r14
0x14000c2d9  jz      short loc_14000C312
0x14000c2db  mov     rcx, rdi; lpsz
0x14000c2de  call    ?FindFileNameFromPath@@YAPEAGPEBG@Z; FindFileNameFromPath(ushort const *)
0x14000c2e3  mov     r8, [rsp+160h+TargetHandle]
0x14000c2e8  mov     [rbp+60h+var_80], rax
0x14000c2ec  mov     eax, 2
0x14000c2f1  mov     [rbp+60h+var_F0.dwUnionChoice], eax
0x14000c2f4  mov     [rbp+60h+var_F0.dwUIChoice], eax
0x14000c2f7  lea     rax, [rbp+60h+var_90]
0x14000c2fb  mov     qword ptr [rbp+60h+var_F0.28h], rax
0x14000c2ff  mov     [rbp+60h+var_90], 48h ; 'H'
0x14000c306  mov     [rbp+60h+var_88], r14
0x14000c30a  mov     [rbp+60h+var_78], rdi
0x14000c30e  mov     [rbp+60h+var_70], r8
0x14000c312  lea     r8, [rsp+160h+var_F0]; struct _WINTRUST_DATA *
0x14000c317  mov     rdx, r12; struct _GUID *
0x14000c31a  mov     rcx, r15; HWND
0x14000c31d  call    ?SpinCallWinVerityTrust@@YAJPEAUHWND__@@PEBU_GUID@@QEAU_WINTRUST_DATA@@@Z; SpinCallWinVerityTrust(HWND__ *,_GUID const *,_WINTRUST_DATA * const)
0x14000c322  mov     ebx, eax
0x14000c324  jmp     short loc_14000C347
0x14000c326  call    cs:__imp_GetLastError
0x14000c32d  nop     dword ptr [rax+rax+00h]
0x14000c332  mov     ebx, eax
0x14000c334  test    eax, eax
0x14000c336  jle     short loc_14000C341
0x14000c338  movzx   ebx, ax
0x14000c33b  or      ebx, 80070000h
0x14000c341  mov     r13d, 1
0x14000c347  mov     rcx, [rsp+160h+TargetHandle]; hObject
0x14000c34c  cmp     ebx, r13d
0x14000c34f  mov     eax, 800B010Bh
0x14000c354  cmovge  ebx, eax
0x14000c357  lea     rdx, [rcx-1]
0x14000c35b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000c35f  ja      short loc_14000C36D
0x14000c361  call    cs:__imp_CloseHandle
0x14000c368  nop     dword ptr [rax+rax+00h]
0x14000c36d  mov     eax, ebx
0x14000c36f  add     rsp, 128h
0x14000c376  pop     r15
0x14000c378  pop     r14
0x14000c37a  pop     r13
0x14000c37c  pop     r12
0x14000c37e  pop     rdi
0x14000c37f  pop     rsi
0x14000c380  pop     rbx
0x14000c381  pop     rbp
0x14000c382  retn
```
