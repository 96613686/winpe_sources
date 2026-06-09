# CDDPDEV::MakeResident(uint,D3DDDI_MAKERESIDENT_FLAGS,unsigned __int64 *,unsigned __int64 *)

- ea: `0x140015ad0`
- end: `0x140015bb3`
- name: `?MakeResident@CDDPDEV@@QEAAJIUD3DDDI_MAKERESIDENT_FLAGS@@PEA_K1@Z`
- size: `227`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this, unsigned int, struct D3DDDI_MAKERESIDENT_FLAGS, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140015764`

## callees

- `0x140015ad0`
- `0x1400372d0`

## pseudocode

```c
__int64 __fastcall CDDPDEV::MakeResident(
        CDDPDEV *this,
        int a2,
        struct D3DDDI_MAKERESIDENT_FLAGS a3,
        unsigned __int64 *a4,
        unsigned __int64 *a5)
{
  __int64 (__fastcall *v5)(_QWORD, __int64, _DWORD *, __int64); // r10
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // r8d
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  unsigned __int64 *v13; // rcx
  _DWORD v15[2]; // [rsp+30h] [rbp-38h] BYREF
  int *v16; // [rsp+38h] [rbp-30h]
  int *v17; // [rsp+40h] [rbp-28h]
  struct D3DDDI_MAKERESIDENT_FLAGS::$2E662C15F8525AEEECC7862586193CD2::$C41099F84E8AA7AB57942996F31C279B v18; // [rsp+48h] [rbp-20h]
  _BYTE v19[20]; // [rsp+4Ch] [rbp-1Ch] BYREF
  int v20; // [rsp+78h] [rbp+10h] BYREF
  int v21; // [rsp+80h] [rbp+18h] BYREF

  v20 = a2;
  v5 = (__int64 (__fastcall *)(_QWORD, __int64, _DWORD *, __int64))*((_QWORD *)this + 55);
  v15[0] = *((_DWORD *)this + 3180);
  memset(v19, 0, sizeof(v19));
  v15[1] = 1;
  v16 = &v20;
  v17 = &v21;
  v21 = 1;
  v18 = a3.0;
  if ( KeGetCurrentThread() == *((struct _KTHREAD **)this + 321) )
    v8 = *((_QWORD *)this + 452);
  else
    v8 = 0;
  v9 = *((_DWORD *)this + 686) >> 12;
  LOBYTE(v9) = (*((_DWORD *)this + 686) & 0x1000) != 0;
  v10 = v5(*((unsigned int *)this + 630), v9, v15, v8);
  if ( v10 == 259 )
  {
    v11 = *((_QWORD *)this + 1596);
    v12 = *(_QWORD *)&v19[4];
    if ( v11 <= *(_QWORD *)&v19[4] )
      v11 = *(_QWORD *)&v19[4];
    *((_QWORD *)this + 1596) = v11;
  }
  else
  {
    v12 = 0;
  }
  v13 = a5;
  *a4 = v12;
  *v13 = *(_QWORD *)&v19[12];
  return v10;
}

```

## disassembly

```asm
0x140015ad0  mov     r11, rsp
0x140015ad3  mov     [r11+8], rbx
0x140015ad7  mov     [rsp+arg_8], edx
0x140015adb  push    rdi
0x140015adc  sub     rsp, 60h
0x140015ae0  mov     eax, [rcx+31B0h]
0x140015ae6  xorps   xmm0, xmm0
0x140015ae9  mov     r10, [rcx+1B8h]
0x140015af0  mov     rdi, r9
0x140015af3  mov     [rsp+68h+var_38], eax
0x140015af7  mov     rbx, rcx
0x140015afa  movdqu  [rsp+68h+var_1C], xmm0
0x140015b00  mov     [rsp+68h+var_C], 0
0x140015b08  lea     rax, [r11+10h]
0x140015b0c  mov     [rsp+68h+var_34], 1
0x140015b14  mov     [r11-30h], rax
0x140015b18  lea     rax, [r11+18h]
0x140015b1c  mov     [r11-28h], rax
0x140015b20  mov     dword ptr [r11+18h], 1
0x140015b28  mov     [r11-20h], r8d
0x140015b2c  mov     rax, gs:188h
0x140015b35  cmp     rax, [rcx+0A08h]
0x140015b3c  jnz     short loc_140015BAE
0x140015b3e  mov     r9, [rcx+0E20h]
0x140015b45  mov     edx, [rcx+0AB8h]
0x140015b4b  lea     r8, [rsp+68h+var_38]
0x140015b50  mov     ecx, [rcx+9D8h]
0x140015b56  mov     rax, r10
0x140015b59  shr     edx, 0Ch
0x140015b5c  and     dl, 1
0x140015b5f  call    _guard_dispatch_icall
0x140015b64  mov     r8d, eax
0x140015b67  cmp     eax, 103h
0x140015b6c  jnz     short loc_140015BAA
0x140015b6e  mov     rcx, [rbx+31E0h]
0x140015b75  mov     rdx, qword ptr [rsp+68h+var_1C+4]
0x140015b7a  cmp     rcx, rdx
0x140015b7d  cmovbe  rcx, rdx
0x140015b81  mov     [rbx+31E0h], rcx
0x140015b88  mov     rcx, [rsp+68h+arg_20]
0x140015b90  mov     [rdi], rdx
0x140015b93  mov     rax, qword ptr [rsp+68h+var_1C+0Ch]
0x140015b98  mov     rbx, [rsp+68h+arg_0]
0x140015b9d  mov     [rcx], rax
0x140015ba0  mov     eax, r8d
0x140015ba3  add     rsp, 60h
0x140015ba7  pop     rdi
0x140015ba8  retn
0x140015baa  xor     edx, edx
0x140015bac  jmp     short loc_140015B88
0x140015bae  xor     r9d, r9d
0x140015bb1  jmp     short loc_140015B45
```
