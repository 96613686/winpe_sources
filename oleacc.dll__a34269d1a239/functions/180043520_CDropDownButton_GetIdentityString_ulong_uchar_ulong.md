# CDropDownButton::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x180043520`
- end: `0x180043591`
- name: `?GetIdentityString@CDropDownButton@@UEAAJKPEAPEAEPEAK@Z`
- size: `113`
- prototype: `__int64 __fastcall(CDropDownButton *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180043520`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043547`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043547`

## pseudocode

```c
__int64 __fastcall CDropDownButton::GetIdentityString(
        CDropDownButton *this,
        int a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  unsigned __int8 *v8; // r10
  __int64 result; // rax
  int v10; // eax
  int v11; // ecx

  *a3 = 0;
  *a4 = 0;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(0x14u);
  if ( !v8 )
    return 2147942414LL;
  v10 = *((_DWORD *)this + 28);
  v11 = *((_DWORD *)this + 24);
  *(_DWORD *)v8 = -2147483647;
  *((_DWORD *)v8 + 1) = v10;
  result = 0;
  *((_DWORD *)v8 + 2) = -4;
  *((_DWORD *)v8 + 3) = v11;
  *((_DWORD *)v8 + 4) = a2;
  *a3 = v8;
  *a4 = 20;
  return result;
}

```

## disassembly

```asm
0x180043520  push    rbx
0x180043522  push    rbp
0x180043523  push    rsi
0x180043524  push    rdi
0x180043525  sub     rsp, 28h
0x180043529  mov     rbx, rcx
0x18004352c  mov     qword ptr [r8], 0
0x180043533  mov     ecx, 14h; cb
0x180043538  mov     dword ptr [r9], 0
0x18004353f  mov     rdi, r9
0x180043542  mov     rsi, r8
0x180043545  mov     ebp, edx
0x180043547  call    cs:__imp_CoTaskMemAlloc
0x18004354d  mov     r10, rax
0x180043550  test    rax, rax
0x180043553  jnz     short loc_18004355C
0x180043555  mov     eax, 8007000Eh
0x18004355a  jmp     short loc_180043588
0x18004355c  mov     eax, [rbx+70h]
0x18004355f  mov     ecx, [rbx+60h]
0x180043562  mov     dword ptr [r10], 80000001h
0x180043569  mov     [r10+4], eax
0x18004356d  xor     eax, eax
0x18004356f  mov     dword ptr [r10+8], 0FFFFFFFCh
0x180043577  mov     [r10+0Ch], ecx
0x18004357b  mov     [r10+10h], ebp
0x18004357f  mov     [rsi], r10
0x180043582  mov     dword ptr [rdi], 14h
0x180043588  add     rsp, 28h
0x18004358c  pop     rdi
0x18004358d  pop     rsi
0x18004358e  pop     rbp
0x18004358f  pop     rbx
0x180043590  retn
```
