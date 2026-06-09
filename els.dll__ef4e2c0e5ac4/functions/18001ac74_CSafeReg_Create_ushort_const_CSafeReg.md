# CSafeReg::Create(ushort const *,CSafeReg *)

- ea: `0x18001ac74`
- end: `0x18001acc8`
- name: `?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z`
- size: `84`
- prototype: `__int64 __fastcall(CSafeReg *__hidden this, const unsigned __int16 *, struct CSafeReg *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010f80`
- `0x1800181f0`
- `0x18001828c`
- `0x180018580`

## callees

- `0x18001ac74`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18001aca7`
- `ADVAPI32!RegCreateKeyExW` at `0x18001aca7`

## pseudocode

```c
__int64 __fastcall CSafeReg::Create(HKEY *this, const unsigned __int16 *a2, HKEY *a3)
{
  HKEY v3; // rcx
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD v7; // [rsp+60h] [rbp+8h] BYREF

  v3 = *this;
  v4 = 0;
  v7 = 0;
  v5 = RegCreateKeyExW(v3, a2, 0, 0, 0, 0x20006u, 0, a3, &v7);
  if ( v5 )
  {
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    else
      return (unsigned int)v5;
  }
  return v4;
}

```

## disassembly

```asm
0x18001ac74  mov     r11, rsp
0x18001ac77  push    rbx
0x18001ac78  sub     rsp, 50h
0x18001ac7c  mov     rcx, [rcx]; hKey
0x18001ac7f  lea     rax, [r11+8]
0x18001ac83  mov     [r11-18h], rax
0x18001ac87  xor     ebx, ebx
0x18001ac89  mov     [r11-20h], r8
0x18001ac8d  xor     r9d, r9d; lpClass
0x18001ac90  mov     [r11-28h], rbx
0x18001ac94  xor     r8d, r8d; Reserved
0x18001ac97  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18001ac9f  mov     [rsp+58h+dwOptions], ebx; dwOptions
0x18001aca3  mov     [rsp+58h+arg_0], ebx
0x18001aca7  call    cs:__imp_RegCreateKeyExW
0x18001acad  test    eax, eax
0x18001acaf  jz      short loc_18001ACC0
0x18001acb1  jg      short loc_18001ACB7
0x18001acb3  mov     ebx, eax
0x18001acb5  jmp     short loc_18001ACC0
0x18001acb7  movzx   ebx, ax
0x18001acba  or      ebx, 80070000h
0x18001acc0  mov     eax, ebx
0x18001acc2  add     rsp, 50h
0x18001acc6  pop     rbx
0x18001acc7  retn
```
