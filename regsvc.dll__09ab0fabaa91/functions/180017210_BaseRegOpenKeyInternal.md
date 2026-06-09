# BaseRegOpenKeyInternal

- ea: `0x180017210`
- end: `0x1800173c6`
- name: `BaseRegOpenKeyInternal`
- size: `438`
- prototype: `ULONG __fastcall(void *, __int64, char, int, char, HANDLE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800199a0`

## callees

- `0x180007740`
- `0x180017210`
- `0x180017688`
- `0x1800176d8`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001739e`
- `ntdll!RtlNtStatusToDosError` at `0x18001739e`
- `ntdll!NtClose` at `0x180017362`
- `ntdll!NtClose` at `0x18001738b`
- `ntdll!NtClose` at `0x180017362`
- `ntdll!NtClose` at `0x18001738b`
- `ntdll!NtQueryKey` at `0x180017357`
- `ntdll!NtQueryKey` at `0x180017357`

## pseudocode

```c
ULONG __fastcall BaseRegOpenKeyInternal(void *a1, __int64 a2, char a3, int a4, char a5, HANDLE *a6)
{
  int v9; // eax
  int v10; // ebx
  int ResultLength; // [rsp+20h] [rbp-B8h]
  HANDLE Handle; // [rsp+30h] [rbp-A8h] BYREF
  ULONG v14; // [rsp+38h] [rbp-A0h] BYREF
  int v15[2]; // [rsp+40h] [rbp-98h] BYREF
  HANDLE v16; // [rsp+48h] [rbp-90h]
  __int64 v17; // [rsp+50h] [rbp-88h]
  int v18; // [rsp+58h] [rbp-80h]
  int v19; // [rsp+5Ch] [rbp-7Ch]
  __int128 v20; // [rsp+60h] [rbp-78h]
  __int128 KeyInformation; // [rsp+70h] [rbp-68h] BYREF
  __int128 v22; // [rsp+80h] [rbp-58h]
  __int64 v23; // [rsp+90h] [rbp-48h]

  Handle = a1;
  v15[1] = 0;
  v19 = 0;
  if ( !a2 || *(_WORD *)a2 < 2u || (*(_BYTE *)a2 & 1) != 0 || !*(_QWORD *)(a2 + 8) || !a6 )
  {
    v10 = -1073741811;
    return RtlNtStatusToDosError(v10);
  }
  *a6 = 0;
  if ( (a5 & 1) != 0 )
  {
    v9 = OpenMachineKey(&Handle);
    goto LABEL_10;
  }
  if ( (a5 & 2) != 0 )
  {
    v9 = OpenUserKey(&Handle);
LABEL_10:
    v10 = v9;
    if ( v9 < 0 )
      return RtlNtStatusToDosError(v10);
  }
  *(_WORD *)a2 -= 2;
  v15[0] = 48;
  v16 = Handle;
  v18 = 32 * (a3 & 8 | 2);
  v17 = a2;
  v20 = 0;
  KeyInformation = 0;
  v22 = 0;
  v23 = 0;
  v14 = 0;
  v10 = Wow64NtOpenKey((int)a6, a4, (int)v15, a3 & 0x1C, ResultLength);
  if ( v10 == 1073741846 )
  {
    v10 = NtQueryKey(*a6, KeyCachedInformation, &KeyInformation, 0x28u, &v14);
    NtClose(*a6);
    if ( v10 >= 0 )
      *a6 = (HANDLE)SDWORD1(v22);
  }
  if ( (a5 & 1) != 0 || (a5 & 2) != 0 )
    NtClose(Handle);
  return RtlNtStatusToDosError(v10);
}

```

## disassembly

```asm
0x180017210  push    rbx
0x180017212  push    rdi
0x180017213  push    r12
0x180017215  push    r13
0x180017217  push    r14
0x180017219  push    r15
0x18001721b  sub     rsp, 0A8h
0x180017222  mov     rax, cs:__security_cookie
0x180017229  xor     rax, rsp
0x18001722c  mov     [rsp+0D8h+var_40], rax
0x180017234  mov     r13d, r9d
0x180017237  mov     r12d, r8d
0x18001723a  mov     r15, rdx
0x18001723d  mov     [rsp+0D8h+Handle], rcx
0x180017242  mov     rdi, qword ptr [rsp+0D8h+arg_28]
0x18001724a  xor     eax, eax
0x18001724c  mov     [rsp+0D8h+var_94], eax
0x180017250  mov     [rsp+0D8h+var_7C], eax
0x180017254  test    rdx, rdx
0x180017257  jz      loc_180017397
0x18001725d  lea     ecx, [rax+2]
0x180017260  cmp     [rdx], cx
0x180017263  jb      loc_180017397
0x180017269  test    byte ptr [rdx], 1
0x18001726c  jnz     loc_180017397
0x180017272  cmp     [rdx+8], rax
0x180017276  jz      loc_180017397
0x18001727c  test    rdi, rdi
0x18001727f  jz      loc_180017397
0x180017285  mov     [rdi], rax
0x180017288  mov     r14d, dword ptr [rsp+0D8h+arg_20]
0x180017290  and     r14d, 1
0x180017294  jz      short loc_1800172A2
0x180017296  lea     rcx, [rsp+0D8h+Handle]
0x18001729b  call    OpenMachineKey
0x1800172a0  jmp     short loc_1800172B5
0x1800172a2  test    [rsp+0D8h+arg_20], cl
0x1800172a9  jz      short loc_1800172C4
0x1800172ab  lea     rcx, [rsp+0D8h+Handle]
0x1800172b0  call    OpenUserKey
0x1800172b5  test    eax, eax
0x1800172b7  mov     ebx, eax
0x1800172b9  js      loc_18001739C
0x1800172bf  mov     ecx, 2
0x1800172c4  mov     eax, 0FFFEh
0x1800172c9  add     [r15], ax
0x1800172cd  mov     [rsp+0D8h+var_98], 30h ; '0'
0x1800172d5  mov     rax, [rsp+0D8h+Handle]
0x1800172da  mov     [rsp+0D8h+var_90], rax
0x1800172df  movzx   eax, r12b
0x1800172e3  and     eax, 8
0x1800172e6  or      eax, ecx
0x1800172e8  shl     eax, 5
0x1800172eb  mov     [rsp+0D8h+var_80], eax
0x1800172ef  mov     [rsp+0D8h+var_88], r15
0x1800172f4  xorps   xmm0, xmm0
0x1800172f7  movdqu  [rsp+0D8h+var_78], xmm0
0x1800172fd  xorps   xmm1, xmm1
0x180017300  xor     eax, eax
0x180017302  movups  [rsp+0D8h+KeyInformation], xmm1
0x180017307  movups  [rsp+0D8h+var_58], xmm1
0x18001730f  mov     [rsp+0D8h+var_48], rax
0x180017317  mov     [rsp+0D8h+var_A0], eax
0x18001731b  and     r12d, 1Ch
0x18001731f  mov     r9d, r12d; int
0x180017322  lea     r8, [rsp+0D8h+var_98]; int
0x180017327  mov     edx, r13d; int
0x18001732a  mov     rcx, rdi; int
0x18001732d  call    Wow64NtOpenKey
0x180017332  mov     ebx, eax
0x180017334  cmp     eax, 40000016h
0x180017339  jnz     short loc_180017377
0x18001733b  lea     rax, [rsp+0D8h+var_A0]
0x180017340  mov     qword ptr [rsp+0D8h+ResultLength], rax; ResultLength
0x180017345  mov     r9d, 28h ; '('; Length
0x18001734b  lea     r8, [rsp+0D8h+KeyInformation]; KeyInformation
0x180017350  lea     edx, [r9-24h]; KeyInformationClass
0x180017354  mov     rcx, [rdi]; KeyHandle
0x180017357  call    cs:__imp_NtQueryKey
0x18001735d  mov     ebx, eax
0x18001735f  mov     rcx, [rdi]; Handle
0x180017362  call    cs:__imp_NtClose
0x180017368  test    ebx, ebx
0x18001736a  js      short loc_180017377
0x18001736c  movsxd  rax, dword ptr [rsp+0D8h+var_58+4]
0x180017374  mov     [rdi], rax
0x180017377  test    r14d, r14d
0x18001737a  jnz     short loc_180017386
0x18001737c  test    [rsp+0D8h+arg_20], 2
0x180017384  jz      short loc_18001739C
0x180017386  mov     rcx, [rsp+0D8h+Handle]; Handle
0x18001738b  call    cs:__imp_NtClose
0x180017391  jmp     short loc_18001739C
0x180017393  mov     ebx, eax
0x180017395  jmp     short loc_18001739C
0x180017397  mov     ebx, 0C000000Dh
0x18001739c  mov     ecx, ebx; Status
0x18001739e  call    cs:__imp_RtlNtStatusToDosError
0x1800173a4  mov     rcx, [rsp+0D8h+var_40]
0x1800173ac  xor     rcx, rsp; StackCookie
0x1800173af  call    __security_check_cookie
0x1800173b4  add     rsp, 0A8h
0x1800173bb  pop     r15
0x1800173bd  pop     r14
0x1800173bf  pop     r13
0x1800173c1  pop     r12
0x1800173c3  pop     rdi
0x1800173c4  pop     rbx
0x1800173c5  retn
```
