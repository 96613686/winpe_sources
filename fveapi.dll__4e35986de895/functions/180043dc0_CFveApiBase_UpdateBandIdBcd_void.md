# CFveApiBase::UpdateBandIdBcd(void)

- ea: `0x180043dc0`
- end: `0x180043efe`
- name: `?UpdateBandIdBcd@CFveApiBase@@QEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180043ce0`

## callees

- `0x180043dc0`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x180043ecc`
- `bcd!BcdCloseObject` at `0x180043ecc`
- `bcd!BcdGetElementData` at `0x180043e76`
- `bcd!BcdGetElementData` at `0x180043e76`
- `bcd!BcdOpenObject` at `0x180043e53`
- `bcd!BcdOpenObject` at `0x180043e53`
- `bcd!BcdCloseStore` at `0x180043eed`
- `bcd!BcdCloseStore` at `0x180043eed`
- `bcd!BcdOpenSystemStore` at `0x180043e32`
- `bcd!BcdOpenSystemStore` at `0x180043e32`
- `bcd!BcdSetElementData` at `0x180043eb5`
- `bcd!BcdSetElementData` at `0x180043eb5`

## pseudocode

```c
__int64 __fastcall CFveApiBase::UpdateBandIdBcd(CFveApiBase *this, __int64 a2)
{
  int v2; // ebx
  bool v3; // zf
  __int64 v5; // rdx
  int ElementData; // eax
  __int64 v7; // [rsp+20h] [rbp-30h] BYREF
  __int64 v8; // [rsp+28h] [rbp-28h] BYREF
  int v9; // [rsp+30h] [rbp-20h] BYREF
  __int64 v10; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF

  v2 = 0;
  v9 = 8;
  v3 = (*((_DWORD *)this + 27) & 0x10000001) == 0;
  v10 = 0;
  v7 = 0;
  v8 = 0;
  if ( v3 || *((_DWORD *)this + 310) == -1 )
    return v2 | 0x10000000u;
  v11 = *((unsigned int *)this + 310);
  v2 = BcdOpenSystemStore(&v8, a2);
  if ( v2 >= 0 )
  {
    v2 = BcdOpenObject(v8, &GUID_CURRENT_BOOT_ENTRY, &v7);
    if ( v2 >= 0 )
    {
      ElementData = BcdGetElementData(v7, 352321612, &v10, &v9);
      v2 = ElementData;
      if ( ElementData >= 0 )
      {
        if ( v10 == v11 )
          goto LABEL_11;
        goto LABEL_10;
      }
      if ( ElementData == -1073741275 )
      {
LABEL_10:
        v9 = 8;
        v2 = BcdSetElementData(v7, 352321612, &v11, 8);
      }
    }
  }
LABEL_11:
  if ( v7 )
  {
    BcdCloseObject(v7);
    v7 = 0;
  }
  if ( v8 )
    BcdCloseStore(v8, v5);
  return v2 | 0x10000000u;
}

```

## disassembly

```asm
0x180043dc0  mov     [rsp-8+arg_8], rbx
0x180043dc5  push    rbp
0x180043dc6  mov     rbp, rsp
0x180043dc9  sub     rsp, 50h
0x180043dcd  mov     rax, cs:__security_cookie
0x180043dd4  xor     rax, rsp
0x180043dd7  mov     [rbp+var_8], rax
0x180043ddb  xor     ebx, ebx
0x180043ddd  mov     [rbp+var_20], 8
0x180043de4  test    dword ptr [rcx+6Ch], 10000001h
0x180043deb  mov     [rbp+var_18], 0
0x180043df3  mov     [rbp+var_30], 0
0x180043dfb  mov     [rbp+var_28], rbx
0x180043dff  jnz     short loc_180043E1F
0x180043e01  bts     ebx, 1Ch
0x180043e05  mov     eax, ebx
0x180043e07  mov     rcx, [rbp+var_8]
0x180043e0b  xor     rcx, rsp; StackCookie
0x180043e0e  call    __security_check_cookie
0x180043e13  mov     rbx, [rsp+50h+arg_8]
0x180043e18  add     rsp, 50h
0x180043e1c  pop     rbp
0x180043e1d  retn
0x180043e1f  mov     eax, [rcx+4D8h]
0x180043e25  cmp     eax, 0FFFFFFFFh
0x180043e28  jz      short loc_180043E01
0x180043e2a  lea     rcx, [rbp+var_28]
0x180043e2e  mov     [rbp+var_10], rax
0x180043e32  call    cs:__imp_BcdOpenSystemStore
0x180043e39  nop     dword ptr [rax+rax+00h]
0x180043e3e  mov     ebx, eax
0x180043e40  test    eax, eax
0x180043e42  js      short loc_180043EC3
0x180043e44  mov     rcx, [rbp+var_28]
0x180043e48  lea     r8, [rbp+var_30]
0x180043e4c  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x180043e53  call    cs:__imp_BcdOpenObject
0x180043e5a  nop     dword ptr [rax+rax+00h]
0x180043e5f  mov     ebx, eax
0x180043e61  test    eax, eax
0x180043e63  js      short loc_180043EC3
0x180043e65  mov     rcx, [rbp+var_30]
0x180043e69  lea     r9, [rbp+var_20]
0x180043e6d  lea     r8, [rbp+var_18]
0x180043e71  mov     edx, 1500004Ch
0x180043e76  call    cs:__imp_BcdGetElementData
0x180043e7d  nop     dword ptr [rax+rax+00h]
0x180043e82  mov     ebx, eax
0x180043e84  test    eax, eax
0x180043e86  js      short loc_180043E94
0x180043e88  mov     rax, [rbp+var_10]
0x180043e8c  cmp     [rbp+var_18], rax
0x180043e90  jnz     short loc_180043E9B
0x180043e92  jmp     short loc_180043EC3
0x180043e94  cmp     eax, 0C0000225h
0x180043e99  jnz     short loc_180043EC3
0x180043e9b  mov     rcx, [rbp+var_30]
0x180043e9f  lea     r8, [rbp+var_10]
0x180043ea3  mov     r9d, 8
0x180043ea9  mov     [rbp+var_20], 8
0x180043eb0  mov     edx, 1500004Ch
0x180043eb5  call    cs:__imp_BcdSetElementData
0x180043ebc  nop     dword ptr [rax+rax+00h]
0x180043ec1  mov     ebx, eax
0x180043ec3  mov     rcx, [rbp+var_30]
0x180043ec7  test    rcx, rcx
0x180043eca  jz      short loc_180043EE0
0x180043ecc  call    cs:__imp_BcdCloseObject
0x180043ed3  nop     dword ptr [rax+rax+00h]
0x180043ed8  mov     [rbp+var_30], 0
0x180043ee0  mov     rcx, [rbp+var_28]
0x180043ee4  test    rcx, rcx
0x180043ee7  jz      loc_180043E01
0x180043eed  call    cs:__imp_BcdCloseStore
0x180043ef4  nop     dword ptr [rax+rax+00h]
0x180043ef9  jmp     loc_180043E01
```
