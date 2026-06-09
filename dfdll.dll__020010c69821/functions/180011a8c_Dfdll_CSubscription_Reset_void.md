# Dfdll::CSubscription::Reset(void)

- ea: `0x180011a8c`
- end: `0x180011b24`
- name: `?Reset@CSubscription@Dfdll@@IEAAJXZ`
- size: `152`
- prototype: `__int64 __fastcall(Dfdll::CSubscription *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008d34`
- `0x18000dadc`
- `0x180010d18`
- `0x180010ea8`

## callees

- `0x180011a8c`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall Dfdll::CSubscription::Reset(Dfdll::CSubscription *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 6);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 6) = 0;
  v3 = *((_QWORD *)this + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  *((_QWORD *)this + 8) = 0;
  v4 = *((_QWORD *)this + 10);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 10) = 0;
  v5 = *((_QWORD *)this + 12);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_QWORD *)this + 12) = 0;
  v6 = *((_QWORD *)this + 14);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  *((_QWORD *)this + 14) = 0;
  return 0;
}

```

## disassembly

```asm
0x180011a8c  push    rbx
0x180011a8e  sub     rsp, 20h
0x180011a92  mov     rbx, rcx
0x180011a95  mov     rcx, [rcx+30h]
0x180011a99  test    rcx, rcx
0x180011a9c  jz      short loc_180011AAB
0x180011a9e  mov     rax, [rcx]
0x180011aa1  mov     rax, [rax+10h]
0x180011aa5  call    cs:__guard_dispatch_icall_fptr
0x180011aab  and     qword ptr [rbx+30h], 0
0x180011ab0  mov     rcx, [rbx+40h]
0x180011ab4  test    rcx, rcx
0x180011ab7  jz      short loc_180011AC6
0x180011ab9  mov     rax, [rcx]
0x180011abc  mov     rax, [rax+10h]
0x180011ac0  call    cs:__guard_dispatch_icall_fptr
0x180011ac6  and     qword ptr [rbx+40h], 0
0x180011acb  mov     rcx, [rbx+50h]
0x180011acf  test    rcx, rcx
0x180011ad2  jz      short loc_180011AE1
0x180011ad4  mov     rax, [rcx]
0x180011ad7  mov     rax, [rax+10h]
0x180011adb  call    cs:__guard_dispatch_icall_fptr
0x180011ae1  and     qword ptr [rbx+50h], 0
0x180011ae6  mov     rcx, [rbx+60h]
0x180011aea  test    rcx, rcx
0x180011aed  jz      short loc_180011AFC
0x180011aef  mov     rax, [rcx]
0x180011af2  mov     rax, [rax+10h]
0x180011af6  call    cs:__guard_dispatch_icall_fptr
0x180011afc  and     qword ptr [rbx+60h], 0
0x180011b01  mov     rcx, [rbx+70h]
0x180011b05  test    rcx, rcx
0x180011b08  jz      short loc_180011B17
0x180011b0a  mov     rax, [rcx]
0x180011b0d  mov     rax, [rax+10h]
0x180011b11  call    cs:__guard_dispatch_icall_fptr
0x180011b17  and     qword ptr [rbx+70h], 0
0x180011b1c  xor     eax, eax
0x180011b1e  add     rsp, 20h
0x180011b22  pop     rbx
0x180011b23  retn
```
