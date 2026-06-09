# IntfDestroyContext

- ea: `0x18001bdc0`
- end: `0x18001bf1e`
- name: `IntfDestroyContext`
- size: `350`
- prototype: `__int64 __fastcall(_LAN_INTERFACE_CONTEXT *this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000a87c`
- `0x18000a9c0`
- `0x18000aa58`
- `0x18000c230`
- `0x180016be4`
- `0x180017158`
- `0x18001bca0`
- `0x18001bdc0`
- `0x1800224ac`
- `0x180032d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001beac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001beac`

## pseudocode

```c
__int64 __fastcall IntfDestroyContext(_LAN_INTERFACE_CONTEXT *this)
{
  struct _LIST_ENTRY *v2; // rcx
  unsigned int v3; // edi
  std::_Ref_count_base *v4; // rcx
  unsigned int v5; // edx
  void *v6; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 39, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( this )
  {
    v3 = 0;
    if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v2[1].Blink) >= 4u && (BYTE4(v2[1].Blink) & 1) != 0 )
      WPP_SF_S(v2[1].Flink, 41, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, *((_QWORD *)this + 15));
    AceDeinitStateMachine((_LAN_INTERFACE_CONTEXT *)((char *)this + 176));
    IntfCleanupUIRequestList(this);
    *((_QWORD *)this + 59) = 0;
    v4 = (std::_Ref_count_base *)*((_QWORD *)this + 60);
    *((_QWORD *)this + 60) = 0;
    if ( v4 )
      std::_Ref_count_base::_Decref(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
    Dot3Free(*((void **)this + 15));
    v6 = (void *)*((_QWORD *)this + 37);
    if ( v6 )
    {
      LpFreeProfile(v6);
      *((_QWORD *)this + 37) = 0;
    }
    _LAN_INTERFACE_CONTEXT::`scalar deleting destructor'(this, v5);
    v2 = WPP_GLOBAL_Control;
  }
  else
  {
    if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v2[1].Blink) && (BYTE4(v2[1].Blink) & 1) != 0 )
    {
      WPP_SF_(v2[1].Flink, 40, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v3 = 87;
  }
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v2[1].Blink) >= 4u && (BYTE4(v2[1].Blink) & 1) != 0 )
    WPP_SF_d(v2[1].Flink, 42, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001bdc0  mov     [rsp+arg_0], rbx
0x18001bdc5  mov     [rsp+arg_8], rdi
0x18001bdca  push    r14
0x18001bdcc  sub     rsp, 20h
0x18001bdd0  mov     rbx, rcx
0x18001bdd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdda  lea     r14, WPP_GLOBAL_Control
0x18001bde1  cmp     rcx, r14
0x18001bde4  jz      short loc_18001BE0E
0x18001bde6  cmp     byte ptr [rcx+19h], 4
0x18001bdea  jb      short loc_18001BE0E
0x18001bdec  test    byte ptr [rcx+1Ch], 1
0x18001bdf0  jz      short loc_18001BE0E
0x18001bdf2  mov     rcx, [rcx+10h]
0x18001bdf6  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001bdfd  mov     edx, 27h ; '''
0x18001be02  call    WPP_SF_
0x18001be07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be0e  test    rbx, rbx
0x18001be11  jnz     short loc_18001BE48
0x18001be13  cmp     rcx, r14
0x18001be16  jz      short loc_18001BE3E
0x18001be18  cmp     byte ptr [rcx+19h], 1
0x18001be1c  jb      short loc_18001BE3E
0x18001be1e  test    byte ptr [rcx+1Ch], 1
0x18001be22  jz      short loc_18001BE3E
0x18001be24  mov     rcx, [rcx+10h]
0x18001be28  lea     edx, [rbx+28h]
0x18001be2b  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001be32  call    WPP_SF_
0x18001be37  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be3e  mov     edi, 57h ; 'W'
0x18001be43  jmp     loc_18001BEE2
0x18001be48  xor     edi, edi
0x18001be4a  cmp     rcx, r14
0x18001be4d  jz      short loc_18001BE72
0x18001be4f  cmp     byte ptr [rcx+19h], 4
0x18001be53  jb      short loc_18001BE72
0x18001be55  test    byte ptr [rcx+1Ch], 1
0x18001be59  jz      short loc_18001BE72
0x18001be5b  mov     r9, [rbx+78h]
0x18001be5f  lea     edx, [rdi+29h]
0x18001be62  mov     rcx, [rcx+10h]
0x18001be66  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001be6d  call    WPP_SF_S
0x18001be72  lea     rcx, [rbx+0B0h]; struct _ACE_STATE_MACHINE *
0x18001be79  call    ?AceDeinitStateMachine@@YAKPEAU_ACE_STATE_MACHINE@@@Z; AceDeinitStateMachine(_ACE_STATE_MACHINE *)
0x18001be7e  mov     rcx, rbx; struct _LAN_INTERFACE_CONTEXT *
0x18001be81  call    ?IntfCleanupUIRequestList@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z; IntfCleanupUIRequestList(_LAN_INTERFACE_CONTEXT *)
0x18001be86  mov     [rbx+1D8h], rdi
0x18001be8d  mov     rcx, [rbx+1E0h]; this
0x18001be94  mov     [rbx+1E0h], rdi
0x18001be9b  test    rcx, rcx
0x18001be9e  jz      short loc_18001BEA5
0x18001bea0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001bea5  lea     rcx, [rbx+80h]; lpCriticalSection
0x18001beac  call    cs:__imp_DeleteCriticalSection
0x18001beb2  mov     rcx, [rbx+78h]; lpMem
0x18001beb6  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001bebb  mov     rcx, [rbx+128h]; lpMem
0x18001bec2  test    rcx, rcx
0x18001bec5  jz      short loc_18001BED3
0x18001bec7  call    LpFreeProfile
0x18001becc  mov     [rbx+128h], rdi
0x18001bed3  mov     rcx, rbx; this
0x18001bed6  call    ??_G_LAN_INTERFACE_CONTEXT@@QEAAPEAXI@Z; _LAN_INTERFACE_CONTEXT::`scalar deleting destructor'(uint)
0x18001bedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bee2  cmp     rcx, r14
0x18001bee5  jz      short loc_18001BF0B
0x18001bee7  cmp     byte ptr [rcx+19h], 4
0x18001beeb  jb      short loc_18001BF0B
0x18001beed  test    byte ptr [rcx+1Ch], 1
0x18001bef1  jz      short loc_18001BF0B
0x18001bef3  mov     rcx, [rcx+10h]
0x18001bef7  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001befe  mov     edx, 2Ah ; '*'
0x18001bf03  mov     r9d, edi
0x18001bf06  call    WPP_SF_d
0x18001bf0b  mov     rbx, [rsp+28h+arg_0]
0x18001bf10  mov     eax, edi
0x18001bf12  mov     rdi, [rsp+28h+arg_8]
0x18001bf17  add     rsp, 20h
0x18001bf1b  pop     r14
0x18001bf1d  retn
```
