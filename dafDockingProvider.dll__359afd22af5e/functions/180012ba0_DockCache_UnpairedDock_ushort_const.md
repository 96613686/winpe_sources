# DockCache::UnpairedDock(ushort const *)

- ea: `0x180012ba0`
- end: `0x180012ccc`
- name: `?UnpairedDock@DockCache@@QEAAJPEBG@Z`
- size: `300`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18000a810`

## callees

- `0x18000c308`
- `0x180011c2c`
- `0x180012288`
- `0x180012ba0`
- `0x180012ddc`
- `0x180013600`
- `0x18001ca3e`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012bbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012cb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012cb1`

## pseudocode

```c
__int64 __fastcall DockCache::UnpairedDock(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *a2)
{
  int Dock; // esi
  int v5; // r8d
  struct Dock *v6; // rbx
  _QWORD *v7; // rcx
  char IsAutoConnectDisallowed; // al
  __int64 v9; // rcx
  struct Dock *v11; // [rsp+50h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+60h] [rbp+18h]

  v12 = this;
  EnterCriticalSection(this);
  v11 = 0;
  Dock = DockCache::FindDock((DockCache *)this, a2, &v11);
  if ( Dock >= 0 )
  {
    v6 = v11;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qqS(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, v5, (_DWORD)this, (char)v11, (__int64)a2);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 4u && (*((_BYTE *)v7 + 28) & 1) != 0 )
        WPP_SF_q(v7[2], 26, &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids, v6);
    }
    *((_BYTE *)v6 + 2912) = 0;
    IsAutoConnectDisallowed = Dock::IsAutoConnectDisallowed(v6);
    Dock::UpdateProperties(v6, IsAutoConnectDisallowed);
    v9 = *((_QWORD *)v6 + 365);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)v6 + 365) = 0;
    }
    *((_BYTE *)v6 + 1744) = 0;
    memset_0((char *)v6 + 1752, 0, 0x488u);
  }
  LeaveCriticalSection(this);
  return (unsigned int)Dock;
}

```

## disassembly

```asm
0x180012ba0  mov     [rsp+arg_8], rbx
0x180012ba5  mov     [rsp+arg_18], rbp
0x180012baa  push    rsi
0x180012bab  push    rdi
0x180012bac  push    r15
0x180012bae  sub     rsp, 30h
0x180012bb2  mov     rbp, rdx
0x180012bb5  mov     rdi, rcx
0x180012bb8  mov     [rsp+48h+arg_10], rcx
0x180012bbd  call    cs:__imp_EnterCriticalSection
0x180012bc3  nop
0x180012bc4  mov     [rsp+48h+arg_0], 0
0x180012bcd  lea     r8, [rsp+48h+arg_0]; struct Dock **
0x180012bd2  mov     rdx, rbp; unsigned __int16 *
0x180012bd5  mov     rcx, rdi; this
0x180012bd8  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x180012bdd  mov     esi, eax
0x180012bdf  test    eax, eax
0x180012be1  js      loc_180012CAE
0x180012be7  lea     r15, WPP_GLOBAL_Control
0x180012bee  mov     rbx, [rsp+48h+arg_0]
0x180012bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bfa  cmp     rcx, r15
0x180012bfd  jz      short loc_180012C56
0x180012bff  cmp     byte ptr [rcx+19h], 3
0x180012c03  jb      short loc_180012C2D
0x180012c05  test    byte ptr [rcx+1Ch], 1
0x180012c09  jz      short loc_180012C2D
0x180012c0b  mov     edx, 2Ch ; ','
0x180012c10  mov     [rsp+48h+var_20], rbp
0x180012c15  mov     [rsp+48h+var_28], rbx
0x180012c1a  mov     r9, rdi
0x180012c1d  mov     rcx, [rcx+10h]
0x180012c21  call    WPP_SF_qqS
0x180012c26  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c2d  cmp     rcx, r15
0x180012c30  jz      short loc_180012C56
0x180012c32  cmp     byte ptr [rcx+19h], 4
0x180012c36  jb      short loc_180012C56
0x180012c38  test    byte ptr [rcx+1Ch], 1
0x180012c3c  jz      short loc_180012C56
0x180012c3e  mov     edx, 1Ah
0x180012c43  mov     r9, rbx
0x180012c46  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180012c4d  mov     rcx, [rcx+10h]
0x180012c51  call    WPP_SF_q
0x180012c56  mov     byte ptr [rbx+0B60h], 0
0x180012c5d  mov     rcx, rbx; this
0x180012c60  call    ?IsAutoConnectDisallowed@Dock@@AEBA_NXZ; Dock::IsAutoConnectDisallowed(void)
0x180012c65  mov     dl, al; bool
0x180012c67  mov     rcx, rbx; this
0x180012c6a  call    ?UpdateProperties@Dock@@AEAAX_N@Z; Dock::UpdateProperties(bool)
0x180012c6f  mov     rcx, [rbx+0B68h]
0x180012c76  test    rcx, rcx
0x180012c79  jz      short loc_180012C92
0x180012c7b  mov     rax, [rcx]
0x180012c7e  mov     rax, [rax+10h]
0x180012c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c87  mov     qword ptr [rbx+0B68h], 0
0x180012c92  mov     byte ptr [rbx+6D0h], 0
0x180012c99  lea     rcx, [rbx+6D8h]; void *
0x180012ca0  xor     edx, edx; Val
0x180012ca2  mov     r8d, 488h; Size
0x180012ca8  call    memset_0
0x180012cad  nop
0x180012cae  mov     rcx, rdi; lpCriticalSection
0x180012cb1  call    cs:__imp_LeaveCriticalSection
0x180012cb7  mov     eax, esi
0x180012cb9  mov     rbx, [rsp+48h+arg_8]
0x180012cbe  mov     rbp, [rsp+48h+arg_18]
0x180012cc3  add     rsp, 30h
0x180012cc7  pop     r15
0x180012cc9  pop     rdi
0x180012cca  pop     rsi
0x180012ccb  retn
```
