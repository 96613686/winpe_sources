# GetCNRInfoForDevice(ushort const *,ushort *,ulong *,ulong *)

- ea: `0x1800034b0`
- end: `0x18000355f`
- name: `?GetCNRInfoForDevice@@YAHPEBGPEAGPEAK2@Z`
- size: `175`
- prototype: `__int64 __fastcall(WCHAR *, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e30`

## callees

- `0x1800034b0`
- `0x180005750`

## import_xrefs

- `MPR!WNetGetConnectionW` at `0x180003518`
- `MPR!WNetGetConnectionW` at `0x180003518`

## pseudocode

```c
__int64 __fastcall GetCNRInfoForDevice(WCHAR *a1, unsigned __int16 *a2, unsigned int *a3, unsigned int *a4)
{
  WCHAR *p_LocalName; // r11
  __int64 v7; // rax
  __int64 v8; // rbx
  WCHAR *v9; // rcx
  DWORD ConnectionW; // eax
  WCHAR LocalName; // [rsp+20h] [rbp-18h] BYREF

  p_LocalName = &LocalName;
  v7 = 2147483646;
  v8 = 3;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *p_LocalName++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v9 = p_LocalName - 1;
  if ( v8 )
    v9 = p_LocalName;
  *v9 = 0;
  ConnectionW = WNetGetConnectionW(&LocalName, a2, a3);
  if ( !ConnectionW )
  {
    *a4 = 1;
    return 1;
  }
  if ( ConnectionW == 2250 )
  {
    *a4 = 0;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp+arg_0], rbx
0x1800034b5  push    rdi
0x1800034b6  sub     rsp, 30h
0x1800034ba  mov     rax, cs:__security_cookie
0x1800034c1  xor     rax, rsp
0x1800034c4  mov     [rsp+38h+var_10], rax
0x1800034c9  mov     rdi, r9
0x1800034cc  lea     r11, [rsp+38h+LocalName]
0x1800034d1  mov     r10, rcx
0x1800034d4  mov     eax, 7FFFFFFEh
0x1800034d9  mov     ebx, 3
0x1800034de  xchg    ax, ax
0x1800034e0  test    rax, rax
0x1800034e3  jz      short loc_180003503
0x1800034e5  movzx   ecx, word ptr [r10]
0x1800034e9  test    cx, cx
0x1800034ec  jz      short loc_180003503
0x1800034ee  mov     [r11], cx
0x1800034f2  add     r10, 2
0x1800034f6  add     r11, 2
0x1800034fa  dec     rax
0x1800034fd  sub     rbx, 1
0x180003501  jnz     short loc_1800034E0
0x180003503  lea     rcx, [r11-2]
0x180003507  test    rbx, rbx
0x18000350a  cmovnz  rcx, r11
0x18000350e  xor     eax, eax
0x180003510  mov     [rcx], ax
0x180003513  lea     rcx, [rsp+38h+LocalName]; lpLocalName
0x180003518  call    cs:__imp_WNetGetConnectionW
0x18000351f  nop     dword ptr [rax+rax+00h]
0x180003524  test    eax, eax
0x180003526  jnz     short loc_18000354C
0x180003528  mov     dword ptr [rdi], 1
0x18000352e  mov     eax, 1
0x180003533  mov     rcx, [rsp+38h+var_10]
0x180003538  xor     rcx, rsp; StackCookie
0x18000353b  call    __security_check_cookie
0x180003540  mov     rbx, [rsp+38h+arg_0]
0x180003545  add     rsp, 30h
0x180003549  pop     rdi
0x18000354a  retn
0x18000354c  cmp     eax, 8CAh
0x180003551  jz      short loc_180003557
0x180003553  xor     eax, eax
0x180003555  jmp     short loc_180003533
0x180003557  mov     dword ptr [rdi], 0
0x18000355d  jmp     short loc_18000352E
```
