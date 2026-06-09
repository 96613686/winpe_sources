# Dock::~Dock(void)

- ea: `0x1800112b4`
- end: `0x180011346`
- name: `??1Dock@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(Dock *__hidden this)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180010a94`
- `0x180011220`
- `0x18001134c`
- `0x180011550`
- `0x180011d84`
- `0x1800123fc`
- `0x180012860`
- `0x180013390`
- `0x18001d221`
- `0x18001d413`

## callees

- `0x18000cb40`
- `0x1800112b4`
- `0x18001f010`

## pseudocode

```c
void __fastcall Dock::~Dock(Dock *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      (_DWORD)this,
      (__int64)this);
  }
  v2 = *((_QWORD *)this + 366);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 366) = 0;
  }
  v3 = *((_QWORD *)this + 365);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 365) = 0;
  }
}

```

## disassembly

```asm
0x1800112b4  push    rbx
0x1800112b6  sub     rsp, 30h
0x1800112ba  mov     rbx, rcx
0x1800112bd  lea     rax, WPP_GLOBAL_Control
0x1800112c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112cb  cmp     rcx, rax
0x1800112ce  jz      short loc_1800112FA
0x1800112d0  cmp     byte ptr [rcx+19h], 4
0x1800112d4  jb      short loc_1800112FA
0x1800112d6  test    byte ptr [rcx+1Ch], 1
0x1800112da  jz      short loc_1800112FA
0x1800112dc  mov     edx, 10h
0x1800112e1  mov     [rsp+38h+var_18], rbx
0x1800112e6  mov     r9, rbx
0x1800112e9  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x1800112f0  mov     rcx, [rcx+10h]
0x1800112f4  call    WPP_SF_qS
0x1800112f9  nop
0x1800112fa  mov     rcx, [rbx+0B70h]
0x180011301  test    rcx, rcx
0x180011304  jz      short loc_18001131D
0x180011306  mov     rax, [rcx]
0x180011309  mov     rax, [rax+10h]
0x18001130d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011312  mov     qword ptr [rbx+0B70h], 0
0x18001131d  mov     rcx, [rbx+0B68h]
0x180011324  test    rcx, rcx
0x180011327  jz      short loc_180011340
0x180011329  mov     rax, [rcx]
0x18001132c  mov     rax, [rax+10h]
0x180011330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011335  mov     qword ptr [rbx+0B68h], 0
0x180011340  add     rsp, 30h
0x180011344  pop     rbx
0x180011345  retn
```
