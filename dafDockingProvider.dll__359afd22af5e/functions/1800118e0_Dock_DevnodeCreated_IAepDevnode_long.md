# Dock::DevnodeCreated(IAepDevnode *,long)

- ea: `0x1800118e0`
- end: `0x18001198e`
- name: `?DevnodeCreated@Dock@@QEAAXPEAUIAepDevnode@@J@Z`
- size: `174`
- prototype: `void __fastcall(struct IAepDevnode **this, struct IAepDevnode *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011994`

## callees

- `0x1800118e0`
- `0x180013b24`
- `0x18001f010`

## pseudocode

```c
void __fastcall Dock::DevnodeCreated(struct IAepDevnode **this, struct IAepDevnode *a2, int a3)
{
  struct IAepDevnode *v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids, this, a2, a3);
  }
  v6 = this[365];
  if ( v6 != a2 )
  {
    if ( v6 )
      (*(void (__fastcall **)(struct IAepDevnode *))(*(_QWORD *)v6 + 16LL))(v6);
    this[365] = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IAepDevnode *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  *((_DWORD *)this + 729) = a3;
  *((_BYTE *)this + 2913) = 1;
}

```

## disassembly

```asm
0x1800118e0  mov     [rsp+arg_0], rbx
0x1800118e5  mov     [rsp+arg_8], rsi
0x1800118ea  push    rdi
0x1800118eb  sub     rsp, 30h
0x1800118ef  mov     esi, r8d
0x1800118f2  mov     rdi, rdx
0x1800118f5  mov     rbx, rcx
0x1800118f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118ff  lea     rax, WPP_GLOBAL_Control
0x180011906  cmp     rcx, rax
0x180011909  jz      short loc_180011939
0x18001190b  cmp     byte ptr [rcx+19h], 4
0x18001190f  jb      short loc_180011939
0x180011911  test    byte ptr [rcx+1Ch], 1
0x180011915  jz      short loc_180011939
0x180011917  mov     rcx, [rcx+10h]
0x18001191b  mov     edx, 23h ; '#'
0x180011920  mov     [rsp+38h+var_10], r8d
0x180011925  mov     r9, rbx
0x180011928  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x18001192f  mov     [rsp+38h+var_18], rdi
0x180011934  call    WPP_SF_qqd
0x180011939  mov     rcx, [rbx+0B68h]
0x180011940  cmp     rcx, rdi
0x180011943  jz      short loc_180011971
0x180011945  test    rcx, rcx
0x180011948  jz      short loc_180011956
0x18001194a  mov     rax, [rcx]
0x18001194d  mov     rax, [rax+10h]
0x180011951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011956  mov     [rbx+0B68h], rdi
0x18001195d  test    rdi, rdi
0x180011960  jz      short loc_180011971
0x180011962  mov     rax, [rdi]
0x180011965  mov     rcx, rdi
0x180011968  mov     rax, [rax+8]
0x18001196c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011971  mov     [rbx+0B64h], esi
0x180011977  mov     rsi, [rsp+38h+arg_8]
0x18001197c  mov     byte ptr [rbx+0B61h], 1
0x180011983  mov     rbx, [rsp+38h+arg_0]
0x180011988  add     rsp, 30h
0x18001198c  pop     rdi
0x18001198d  retn
```
