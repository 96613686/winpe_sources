# CKsAllocator::KsCreateAllocatorAndGetHandle(IKsPin *)

- ea: `0x1800262d0`
- end: `0x1800264e2`
- name: `?KsCreateAllocatorAndGetHandle@CKsAllocator@@UEAAPEAXPEAUIKsPin@@@Z`
- size: `530`
- prototype: `IMemAllocatorCallbackTemp_vtbl *__fastcall(CKsAllocator *this, struct IKsPin *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002b58`
- `0x18001f620`
- `0x1800262d0`
- `0x180026638`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026459`
- `KERNEL32!GetLastError` at `0x180026459`
- `KERNEL32!CloseHandle` at `0x180026317`
- `KERNEL32!CloseHandle` at `0x180026317`
- `ksuser!KsCreateAllocator` at `0x180026449`
- `ksuser!KsCreateAllocator` at `0x180026449`

## pseudocode

```c
IMemAllocatorCallbackTemp_vtbl *__fastcall CKsAllocator::KsCreateAllocatorAndGetHandle(
        CKsAllocator *this,
        struct IKsPin *a2)
{
  IMemAllocatorCallbackTemp *v2; // rdi
  IMemAllocatorCallbackTemp_vtbl *v4; // rcx
  IKsPin_vtbl *v6; // rax
  void *v7; // r14
  ULONG v8; // eax
  __int64 v9; // rbx
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  signed int LastError; // eax
  __int64 v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  $9FE49925FA283FF41E52F8633C4A0042 AllocatorFraming; // [rsp+60h] [rbp-20h] BYREF

  v2 = &this->IMemAllocatorCallbackTemp;
  v4 = this->CMemAllocator::CBaseAllocator::IMemAllocatorCallbackTemp::IMemAllocator::IUnknown::__vftable;
  v15 = 0;
  memset(&AllocatorFraming, 0, sizeof(AllocatorFraming));
  if ( v4 )
  {
    CloseHandle(v4);
    v2->__vftable = 0;
  }
  v6 = a2->__vftable;
  v16 = 0;
  if ( v6->QueryInterface(a2, &GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1, (void **)&v16) < 0 )
    return 0;
  v7 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 24LL))(v16);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( !v7 || a2->QueryInterface(a2, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v15) < 0 )
    return 0;
  AllocatorFraming.Frames = this->m_CritSec.LockCount;
  AllocatorFraming.FrameSize = this->m_CritSec.RecursionCount;
  v8 = LODWORD(this->m_CritSec.OwningThread) - 1;
  AllocatorFraming.OptionsFlags = 2;
  AllocatorFraming.FileAlignment = v8;
  AllocatorFraming.PoolType = this->m_AllocatorPropertiesEx.MemoryType.Data1 == 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 96LL))(v15);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 104LL))(v15);
    WPP_SF_SSqdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v12,
      v10,
      v9,
      (char)a2,
      AllocatorFraming.Frames,
      AllocatorFraming.FrameSize,
      AllocatorFraming.FramePitch,
      AllocatorFraming.OptionsFlags);
  }
  if ( KsCreateAllocator(v7, &AllocatorFraming, (PHANDLE)&v2->__vftable) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v2->__vftable = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_fe7a9118b06232fec4bd8b1a4538b614_Traceguids,
        (unsigned int)LastError);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return v2->__vftable;
}

```

## disassembly

```asm
0x1800262d0  mov     [rsp-28h+arg_10], rbx
0x1800262d5  push    rbp
0x1800262d6  push    rsi
0x1800262d7  push    rdi
0x1800262d8  push    r12
0x1800262da  push    r14
0x1800262dc  mov     rbp, rsp
0x1800262df  sub     rsp, 80h
0x1800262e6  mov     rax, cs:__security_cookie
0x1800262ed  xor     rax, rsp
0x1800262f0  mov     [rbp+var_8], rax
0x1800262f4  xor     eax, eax
0x1800262f6  lea     rdi, [rcx+18h]
0x1800262fa  mov     rbx, rcx
0x1800262fd  mov     qword ptr [rbp+AllocatorFraming.10h], rax
0x180026301  mov     rcx, [rdi]; hObject
0x180026304  xorps   xmm0, xmm0
0x180026307  mov     [rbp+var_30], rax
0x18002630b  mov     rsi, rdx
0x18002630e  movups  xmmword ptr [rbp+AllocatorFraming], xmm0
0x180026312  test    rcx, rcx
0x180026315  jz      short loc_18002632A
0x180026317  call    cs:__imp_CloseHandle
0x18002631e  nop     dword ptr [rax+rax+00h]
0x180026323  mov     qword ptr [rdi], 0
0x18002632a  mov     rax, [rsi]
0x18002632d  lea     r8, [rbp+var_28]
0x180026331  lea     rdx, _GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x180026338  mov     [rbp+var_28], 0
0x180026340  mov     rcx, rsi
0x180026343  mov     rax, [rax]
0x180026346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002634b  test    eax, eax
0x18002634d  js      loc_1800264BC
0x180026353  mov     rcx, [rbp+var_28]
0x180026357  mov     rax, [rcx]
0x18002635a  mov     rax, [rax+18h]
0x18002635e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026363  mov     rcx, [rbp+var_28]
0x180026367  mov     r14, rax
0x18002636a  mov     rax, [rcx]
0x18002636d  mov     rax, [rax+10h]
0x180026371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026376  test    r14, r14
0x180026379  jz      loc_1800264BC
0x18002637f  mov     rax, [rsi]
0x180026382  lea     r8, [rbp+var_30]
0x180026386  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x18002638d  mov     rcx, rsi
0x180026390  mov     rax, [rax]
0x180026393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026398  test    eax, eax
0x18002639a  js      loc_1800264BC
0x1800263a0  mov     eax, [rbx+28h]
0x1800263a3  mov     [rbp+AllocatorFraming.Frames], eax
0x1800263a6  mov     eax, [rbx+2Ch]
0x1800263a9  mov     [rbp+AllocatorFraming.FrameSize], eax
0x1800263ac  mov     eax, [rbx+30h]
0x1800263af  dec     eax
0x1800263b1  mov     dword ptr [rbp+AllocatorFraming], 2
0x1800263b8  mov     dword ptr [rbp+AllocatorFraming.10h], eax
0x1800263bb  xor     eax, eax
0x1800263bd  cmp     dword ptr [rbx+0D8h], 1
0x1800263c4  setz    al
0x1800263c7  mov     [rbp+AllocatorFraming.PoolType], eax
0x1800263ca  mov     rax, cs:WPP_GLOBAL_Control
0x1800263d1  lea     r12, WPP_GLOBAL_Control
0x1800263d8  cmp     rax, r12
0x1800263db  jz      short loc_18002643F
0x1800263dd  cmp     byte ptr [rax+19h], 2
0x1800263e1  jb      short loc_18002643F
0x1800263e3  mov     rcx, [rbp+var_30]
0x1800263e7  mov     rax, [rcx]
0x1800263ea  mov     rax, [rax+60h]
0x1800263ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263f3  mov     rcx, [rbp+var_30]
0x1800263f7  mov     rbx, rax
0x1800263fa  mov     rax, [rcx]
0x1800263fd  mov     rax, [rax+68h]
0x180026401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026406  mov     rcx, cs:WPP_GLOBAL_Control
0x18002640d  mov     r9, rax
0x180026410  mov     eax, dword ptr [rbp+AllocatorFraming]
0x180026413  mov     [rsp+80h+var_38], eax
0x180026417  mov     eax, dword ptr [rbp+AllocatorFraming.10h]
0x18002641a  mov     rcx, [rcx+10h]
0x18002641e  mov     [rsp+80h+var_40], eax
0x180026422  mov     eax, [rbp+AllocatorFraming.FrameSize]
0x180026425  mov     [rsp+80h+var_48], eax
0x180026429  mov     eax, [rbp+AllocatorFraming.Frames]
0x18002642c  mov     [rsp+80h+var_50], eax
0x180026430  mov     [rsp+80h+var_58], rsi
0x180026435  mov     [rsp+80h+var_60], rbx
0x18002643a  call    WPP_SF_SSqdddD
0x18002643f  mov     r8, rdi; AllocatorHandle
0x180026442  lea     rdx, [rbp+AllocatorFraming]; AllocatorFraming
0x180026446  mov     rcx, r14; ConnectionHandle
0x180026449  call    cs:__imp_KsCreateAllocator
0x180026450  nop     dword ptr [rax+rax+00h]
0x180026455  test    eax, eax
0x180026457  jz      short loc_1800264A2
0x180026459  call    cs:__imp_GetLastError
0x180026460  nop     dword ptr [rax+rax+00h]
0x180026465  test    eax, eax
0x180026467  jle     short loc_180026471
0x180026469  movzx   eax, ax
0x18002646c  or      eax, 80070000h
0x180026471  mov     qword ptr [rdi], 0
0x180026478  mov     rcx, cs:WPP_GLOBAL_Control
0x18002647f  cmp     rcx, r12
0x180026482  jz      short loc_1800264A2
0x180026484  cmp     byte ptr [rcx+19h], 2
0x180026488  jb      short loc_1800264A2
0x18002648a  mov     rcx, [rcx+10h]
0x18002648e  lea     r8, WPP_fe7a9118b06232fec4bd8b1a4538b614_Traceguids
0x180026495  mov     edx, 0Dh
0x18002649a  mov     r9d, eax
0x18002649d  call    WPP_SF_d
0x1800264a2  mov     rcx, [rbp+var_30]
0x1800264a6  test    rcx, rcx
0x1800264a9  jz      short loc_1800264B7
0x1800264ab  mov     rdx, [rcx]
0x1800264ae  mov     rax, [rdx+10h]
0x1800264b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264b7  mov     rax, [rdi]
0x1800264ba  jmp     short loc_1800264BE
0x1800264bc  xor     eax, eax
0x1800264be  mov     rcx, [rbp+var_8]
0x1800264c2  xor     rcx, rsp; StackCookie
0x1800264c5  call    __security_check_cookie
0x1800264ca  mov     rbx, [rsp+80h+arg_10]
0x1800264d2  add     rsp, 80h
0x1800264d9  pop     r14
0x1800264db  pop     r12
0x1800264dd  pop     rdi
0x1800264de  pop     rsi
0x1800264df  pop     rbp
0x1800264e0  retn
```
