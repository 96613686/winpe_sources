# CCertEncodeCRLDistInfo::_MapDistPoint(int,long,long * *,_CERT_ALT_NAME_ENTRY * * *)

- ea: `0x180008414`
- end: `0x180008460`
- name: `?_MapDistPoint@CCertEncodeCRLDistInfo@@AEAAJHJPEAPEAJPEAPEAPEAU_CERT_ALT_NAME_ENTRY@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(CCertEncodeCRLDistInfo *__hidden this, int, int, int **, struct _CERT_ALT_NAME_ENTRY ***)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007c60`
- `0x1800081f0`

## callees

- `0x180008414`

## pseudocode

```c
__int64 __fastcall CCertEncodeCRLDistInfo::_MapDistPoint(
        CCertEncodeCRLDistInfo *this,
        int a2,
        int a3,
        int **a4,
        struct _CERT_ALT_NAME_ENTRY ***a5)
{
  __int64 v5; // r10
  unsigned int v6; // edx
  __int64 v7; // rcx

  if ( !a2 || *((_DWORD *)this + 22) )
    v5 = *((_QWORD *)this + 8);
  else
    v5 = 0;
  if ( v5 && a3 >= 0 && *((_DWORD *)this + 18) > a3 )
  {
    v6 = 0;
    v7 = v5 + ((__int64)a3 << 6) + 8;
    *a4 = (int *)v7;
    *a5 = (struct _CERT_ALT_NAME_ENTRY **)(v7 + 8);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180008414  test    edx, edx
0x180008416  jz      short loc_180008423
0x180008418  cmp     dword ptr [rcx+58h], 0
0x18000841c  jnz     short loc_180008423
0x18000841e  xor     r10d, r10d
0x180008421  jmp     short loc_180008427
0x180008423  mov     r10, [rcx+40h]
0x180008427  test    r10, r10
0x18000842a  jz      short loc_180008458
0x18000842c  test    r8d, r8d
0x18000842f  js      short loc_180008458
0x180008431  cmp     [rcx+48h], r8d
0x180008435  jle     short loc_180008458
0x180008437  mov     rax, [rsp+arg_20]
0x18000843c  xor     edx, edx
0x18000843e  movsxd  rcx, r8d
0x180008441  shl     rcx, 6
0x180008445  add     rcx, 8
0x180008449  add     rcx, r10
0x18000844c  mov     [r9], rcx
0x18000844f  add     rcx, 8
0x180008453  mov     [rax], rcx
0x180008456  jmp     short loc_18000845D
0x180008458  mov     edx, 80070057h
0x18000845d  mov     eax, edx
0x18000845f  retn
```
