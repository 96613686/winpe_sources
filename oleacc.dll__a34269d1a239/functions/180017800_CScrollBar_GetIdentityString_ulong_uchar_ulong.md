# CScrollBar::GetIdentityString(ulong,uchar * *,ulong *)

- ea: `0x180017800`
- end: `0x180017872`
- name: `?GetIdentityString@CScrollBar@@UEAAJKPEAPEAEPEAK@Z`
- size: `114`
- prototype: `__int64 __fastcall(CScrollBar *__hidden this, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180017800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017827`

## pseudocode

```c
__int64 __fastcall CScrollBar::GetIdentityString(CScrollBar *this, int a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned __int8 *v8; // r10
  bool v9; // cf
  int v10; // eax
  __int64 result; // rax

  *a3 = 0;
  *a4 = 0;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
  if ( !v8 )
    return 2147942414LL;
  v9 = *((_DWORD *)this + 24) != 0;
  v10 = *((_DWORD *)this + 12);
  *(_DWORD *)v8 = -2147483647;
  *((_DWORD *)v8 + 1) = v10;
  *((_DWORD *)v8 + 2) = v9 - 6;
  result = 0;
  *((_DWORD *)v8 + 3) = a2;
  *a3 = v8;
  *a4 = 16;
  return result;
}

```

## disassembly

```asm
0x180017800  push    rbx
0x180017802  push    rbp
0x180017803  push    rsi
0x180017804  push    rdi
0x180017805  sub     rsp, 28h
0x180017809  mov     rbx, rcx
0x18001780c  mov     qword ptr [r8], 0
0x180017813  mov     ecx, 10h; cb
0x180017818  mov     dword ptr [r9], 0
0x18001781f  mov     rdi, r9
0x180017822  mov     rsi, r8
0x180017825  mov     ebp, edx
0x180017827  call    cs:__imp_CoTaskMemAlloc
0x18001782d  mov     r10, rax
0x180017830  test    rax, rax
0x180017833  jz      short loc_18001786B
0x180017835  mov     eax, [rbx+60h]
0x180017838  neg     eax
0x18001783a  mov     eax, [rbx+30h]
0x18001783d  mov     dword ptr [r10], 80000001h
0x180017844  sbb     ecx, ecx
0x180017846  mov     [r10+4], eax
0x18001784a  neg     ecx
0x18001784c  add     ecx, 0FFFFFFFAh
0x18001784f  mov     [r10+8], ecx
0x180017853  xor     eax, eax
0x180017855  mov     [r10+0Ch], ebp
0x180017859  mov     [rsi], r10
0x18001785c  mov     dword ptr [rdi], 10h
0x180017862  add     rsp, 28h
0x180017866  pop     rdi
0x180017867  pop     rsi
0x180017868  pop     rbp
0x180017869  pop     rbx
0x18001786a  retn
0x18001786b  mov     eax, 8007000Eh
0x180017870  jmp     short loc_180017862
```
