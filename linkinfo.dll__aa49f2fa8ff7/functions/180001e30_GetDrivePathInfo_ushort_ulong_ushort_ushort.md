# GetDrivePathInfo(ushort *,ulong *,ushort *,ushort * *)

- ea: `0x180001e30`
- end: `0x180001eff`
- name: `?GetDrivePathInfo@@YAHPEAGPEAK0PEAPEAG@Z`
- size: `207`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ce0`

## callees

- `0x180001e30`
- `0x1800034b0`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180001ea8`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180001ea8`

## pseudocode

```c
__int64 __fastcall GetDrivePathInfo(
        unsigned __int16 *a1,
        unsigned int *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  WCHAR *p_RootPathName; // r9
  unsigned __int16 *v8; // r8
  __int64 v9; // rdx
  __int64 v11; // r10
  WCHAR *v12; // rcx
  __int64 result; // rax
  unsigned int v14; // [rsp+20h] [rbp-38h] BYREF
  WCHAR RootPathName; // [rsp+28h] [rbp-30h] BYREF

  *a2 = 0;
  p_RootPathName = &RootPathName;
  v8 = a1;
  v9 = 2147483646;
  v11 = 4;
  do
  {
    if ( !v9 )
      break;
    if ( !*v8 )
      break;
    *p_RootPathName++ = *v8++;
    --v9;
    --v11;
  }
  while ( v11 );
  v12 = p_RootPathName - 1;
  if ( v11 )
    v12 = p_RootPathName;
  *v12 = 0;
  if ( GetDriveTypeW(&RootPathName) == 4 )
  {
    v14 = 260;
    result = GetCNRInfoForDevice(&RootPathName, a3, &v14, a2);
  }
  else
  {
    result = 1;
  }
  *a4 = a1 + 3;
  return result;
}

```

## disassembly

```asm
0x180001e30  mov     [rsp+arg_0], rbx
0x180001e35  push    rbp
0x180001e36  push    rsi
0x180001e37  push    rdi
0x180001e38  sub     rsp, 40h
0x180001e3c  mov     rax, cs:__security_cookie
0x180001e43  xor     rax, rsp
0x180001e46  mov     [rsp+58h+var_28], rax
0x180001e4b  mov     rdi, r9
0x180001e4e  mov     dword ptr [rdx], 0
0x180001e54  mov     rbp, r8
0x180001e57  lea     r9, [rsp+58h+RootPathName]
0x180001e5c  mov     rsi, rdx
0x180001e5f  mov     r8, rcx
0x180001e62  mov     edx, 7FFFFFFEh
0x180001e67  mov     rbx, rcx
0x180001e6a  mov     r10d, 4
0x180001e70  test    rdx, rdx
0x180001e73  jz      short loc_180001E93
0x180001e75  movzx   eax, word ptr [r8]
0x180001e79  test    ax, ax
0x180001e7c  jz      short loc_180001E93
0x180001e7e  mov     [r9], ax
0x180001e82  add     r8, 2
0x180001e86  add     r9, 2
0x180001e8a  dec     rdx
0x180001e8d  sub     r10, 1
0x180001e91  jnz     short loc_180001E70
0x180001e93  test    r10, r10
0x180001e96  lea     rcx, [r9-2]
0x180001e9a  cmovnz  rcx, r9
0x180001e9e  xor     eax, eax
0x180001ea0  mov     [rcx], ax
0x180001ea3  lea     rcx, [rsp+58h+RootPathName]; lpRootPathName
0x180001ea8  call    cs:__imp_GetDriveTypeW
0x180001eaf  nop     dword ptr [rax+rax+00h]
0x180001eb4  cmp     eax, 4
0x180001eb7  jz      short loc_180001EE0
0x180001eb9  mov     eax, 1
0x180001ebe  lea     rcx, [rbx+6]
0x180001ec2  mov     [rdi], rcx
0x180001ec5  mov     rcx, [rsp+58h+var_28]
0x180001eca  xor     rcx, rsp; StackCookie
0x180001ecd  call    __security_check_cookie
0x180001ed2  mov     rbx, [rsp+58h+arg_0]
0x180001ed7  add     rsp, 40h
0x180001edb  pop     rdi
0x180001edc  pop     rsi
0x180001edd  pop     rbp
0x180001ede  retn
0x180001ee0  mov     r9, rsi; unsigned int *
0x180001ee3  mov     [rsp+58h+var_38], 104h
0x180001eeb  lea     r8, [rsp+58h+var_38]; unsigned int *
0x180001ef0  mov     rdx, rbp; unsigned __int16 *
0x180001ef3  lea     rcx, [rsp+58h+RootPathName]; unsigned __int16 *
0x180001ef8  call    ?GetCNRInfoForDevice@@YAHPEBGPEAGPEAK2@Z; GetCNRInfoForDevice(ushort const *,ushort *,ulong *,ulong *)
0x180001efd  jmp     short loc_180001EBE
```
