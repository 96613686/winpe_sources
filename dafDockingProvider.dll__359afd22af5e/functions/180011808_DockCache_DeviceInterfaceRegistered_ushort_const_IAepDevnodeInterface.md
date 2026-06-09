# DockCache::DeviceInterfaceRegistered(ushort const *,IAepDevnodeInterface *)

- ea: `0x180011808`
- end: `0x1800118d9`
- name: `?DeviceInterfaceRegistered@DockCache@@QEAAXPEBGPEAUIAepDevnodeInterface@@@Z`
- size: `209`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, struct IAepDevnodeInterface *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e7d0`

## callees

- `0x180011808`
- `0x180011c2c`
- `0x180013788`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011822`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011822`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800118d2`

## pseudocode

```c
void __fastcall DockCache::DeviceInterfaceRegistered(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        struct IAepDevnodeInterface *a3)
{
  int v6; // r8d
  struct Dock *v7; // rdi
  struct IAepDevnodeInterface *v8; // rcx
  struct Dock *v9; // [rsp+60h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+78h] [rbp+20h]

  v10 = this;
  EnterCriticalSection(this);
  v9 = 0;
  if ( DockCache::FindDock((DockCache *)this, a2, &v9) >= 0 )
  {
    v7 = v9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqSq(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, v6, (_DWORD)this, (char)v9, (__int64)a2, (char)a3);
    }
    v8 = (struct IAepDevnodeInterface *)*((_QWORD *)v7 + 366);
    if ( v8 != a3 )
    {
      if ( v8 )
        (*(void (__fastcall **)(struct IAepDevnodeInterface *))(*(_QWORD *)v8 + 16LL))(v8);
      *((_QWORD *)v7 + 366) = a3;
      if ( a3 )
        (*(void (__fastcall **)(struct IAepDevnodeInterface *))(*(_QWORD *)a3 + 8LL))(a3);
    }
  }
  LeaveCriticalSection(this);
}

```

## disassembly

```asm
0x180011808  mov     [rsp+arg_8], rbx
0x18001180d  push    rbp
0x18001180e  push    rsi
0x18001180f  push    rdi
0x180011810  sub     rsp, 40h
0x180011814  mov     rbx, r8
0x180011817  mov     rbp, rdx
0x18001181a  mov     rsi, rcx
0x18001181d  mov     [rsp+58h+arg_18], rcx
0x180011822  call    cs:__imp_EnterCriticalSection
0x180011828  nop
0x180011829  mov     [rsp+58h+arg_0], 0
0x180011832  lea     r8, [rsp+58h+arg_0]; struct Dock **
0x180011837  mov     rdx, rbp; unsigned __int16 *
0x18001183a  mov     rcx, rsi; this
0x18001183d  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x180011842  test    eax, eax
0x180011844  js      short loc_1800118C3
0x180011846  lea     rax, WPP_GLOBAL_Control
0x18001184d  mov     rdi, [rsp+58h+arg_0]
0x180011852  mov     rcx, cs:WPP_GLOBAL_Control
0x180011859  cmp     rcx, rax
0x18001185c  jz      short loc_18001188A
0x18001185e  cmp     byte ptr [rcx+19h], 3
0x180011862  jb      short loc_18001188A
0x180011864  test    byte ptr [rcx+1Ch], 1
0x180011868  jz      short loc_18001188A
0x18001186a  mov     edx, 41h ; 'A'
0x18001186f  mov     [rsp+58h+var_28], rbx
0x180011874  mov     [rsp+58h+var_30], rbp
0x180011879  mov     [rsp+58h+var_38], rdi
0x18001187e  mov     r9, rsi
0x180011881  mov     rcx, [rcx+10h]
0x180011885  call    WPP_SF_qqSq
0x18001188a  mov     rcx, [rdi+0B70h]
0x180011891  cmp     rcx, rbx
0x180011894  jz      short loc_1800118C3
0x180011896  test    rcx, rcx
0x180011899  jz      short loc_1800118A7
0x18001189b  mov     rax, [rcx]
0x18001189e  mov     rax, [rax+10h]
0x1800118a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a7  mov     [rdi+0B70h], rbx
0x1800118ae  test    rbx, rbx
0x1800118b1  jz      short loc_1800118C3
0x1800118b3  mov     rax, [rbx]
0x1800118b6  mov     rcx, rbx
0x1800118b9  mov     rax, [rax+8]
0x1800118bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c2  nop
0x1800118c3  mov     rcx, rsi
0x1800118c6  mov     rbx, [rsp+58h+arg_8]
0x1800118cb  add     rsp, 40h
0x1800118cf  pop     rdi
0x1800118d0  pop     rsi
0x1800118d1  pop     rbp
0x1800118d2  jmp     cs:__imp_LeaveCriticalSection
```
