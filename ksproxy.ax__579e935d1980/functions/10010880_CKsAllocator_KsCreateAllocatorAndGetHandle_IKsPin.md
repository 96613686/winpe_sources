# CKsAllocator::KsCreateAllocatorAndGetHandle(IKsPin *)

- ea: `0x10010880`
- end: `0x10010a3b`
- name: `?KsCreateAllocatorAndGetHandle@CKsAllocator@@UAGPAXPAUIKsPin@@@Z`
- size: `443`
- prototype: `void *__stdcall(CKsAllocator *__hidden this, struct IKsPin *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1000665f`
- `0x100105f4`
- `0x10010880`
- `0x1002d510`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100109ca`
- `KERNEL32!GetLastError` at `0x100109ca`
- `KERNEL32!CloseHandle` at `0x100108af`
- `KERNEL32!CloseHandle` at `0x100108af`
- `ksuser!KsCreateAllocator` at `0x100109c0`
- `ksuser!KsCreateAllocator` at `0x100109c0`

## pseudocode

```c
IMemAllocatorCallbackTemp_vtbl *__stdcall CKsAllocator::KsCreateAllocatorAndGetHandle(
        CKsAllocator *this,
        struct IKsPin *a2)
{
  struct IKsPin *v2; // ecx
  IMemAllocatorCallbackTemp *v3; // ebx
  char *v4; // eax
  int v5; // edi
  int v6; // eax
  char LastError; // al
  HANDLE ConnectionHandle; // [esp+Ch] [ebp-2Ch]
  int v10; // [esp+10h] [ebp-28h] BYREF
  char v11[4]; // [esp+14h] [ebp-24h]
  int v12; // [esp+18h] [ebp-20h] BYREF
  $9FE49925FA283FF41E52F8633C4A0042 AllocatorFraming; // [esp+1Ch] [ebp-1Ch] BYREF

  v2 = a2;
  *(_DWORD *)v11 = a2;
  v12 = 0;
  v3 = &this->IMemAllocatorCallbackTemp;
  if ( this->CMemAllocator::CBaseAllocator::IMemAllocatorCallbackTemp::IMemAllocator::IUnknown::__vftable )
  {
    CloseHandle(v3->__vftable);
    v2 = *(struct IKsPin **)v11;
    v3->__vftable = 0;
  }
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), struct IKsPin *, GUID *, int *))v2->QueryInterface)(
         v2->QueryInterface,
         v2,
         &_GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1,
         &v10) < 0 )
    return 0;
  ConnectionHandle = (HANDLE)(*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v10 + 12))(
                               *(_DWORD *)(*(_DWORD *)v10 + 12),
                               v10);
  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v10 + 8))(*(_DWORD *)(*(_DWORD *)v10 + 8), v10);
  if ( !ConnectionHandle
    || (***(int (__thiscall ****)(_DWORD, _DWORD, GUID *, int *))v11)(
         ***(_DWORD ***)v11,
         *(_DWORD *)v11,
         &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
         &v12) < 0 )
  {
    return 0;
  }
  AllocatorFraming.Frames = this->m_CritSec.LockCount;
  AllocatorFraming.FrameSize = this->m_CritSec.RecursionCount;
  v4 = (char *)this->m_CritSec.OwningThread - 1;
  AllocatorFraming.OptionsFlags = 2;
  AllocatorFraming.FileAlignment = (ULONG)v4;
  AllocatorFraming.PoolType = this->m_AllocatorPropertiesEx.Input.OptimalRange.Range.MinFrameSize == 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v12 + 48))(*(_DWORD *)(*(_DWORD *)v12 + 48), v12);
    v6 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v12 + 52))(*(_DWORD *)(*(_DWORD *)v12 + 52), v12);
    WPP_SF_SSqdddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      v5,
      v11[0],
      AllocatorFraming.Frames,
      AllocatorFraming.FrameSize,
      AllocatorFraming.FramePitch,
      AllocatorFraming.OptionsFlags);
  }
  if ( KsCreateAllocator(ConnectionHandle, &AllocatorFraming, (PHANDLE)&v3->__vftable) )
  {
    LastError = GetLastError();
    v3->__vftable = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_q(0xDu, &WPP_fe7a9118b06232fec4bd8b1a4538b614_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
  }
  if ( v12 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v12 + 8))(*(_DWORD *)(*(_DWORD *)v12 + 8), v12);
  return v3->__vftable;
}

```

## disassembly

```asm
0x10010880  mov     edi, edi
0x10010882  push    ebp
0x10010883  mov     ebp, esp
0x10010885  sub     esp, 2Ch
0x10010888  mov     eax, ___security_cookie
0x1001088d  xor     eax, ebp
0x1001088f  mov     [ebp+var_4], eax
0x10010892  mov     ecx, [ebp+arg_4]
0x10010895  push    ebx
0x10010896  push    esi
0x10010897  push    edi
0x10010898  mov     edi, [ebp+this]
0x1001089b  mov     dword ptr [ebp+var_24], ecx
0x1001089e  mov     [ebp+var_20], 0
0x100108a5  lea     ebx, [edi+0Ch]
0x100108a8  cmp     dword ptr [ebx], 0
0x100108ab  jz      short loc_100108BE
0x100108ad  push    dword ptr [ebx]; hObject
0x100108af  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100108b5  mov     ecx, dword ptr [ebp+var_24]
0x100108b8  mov     dword ptr [ebx], 0
0x100108be  mov     eax, [ecx]
0x100108c0  mov     esi, [eax]
0x100108c2  lea     eax, [ebp+var_28]
0x100108c5  push    eax
0x100108c6  push    offset __GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x100108cb  push    ecx
0x100108cc  mov     ecx, esi; this
0x100108ce  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100108d4  call    esi
0x100108d6  test    eax, eax
0x100108d8  js      loc_10010A28
0x100108de  mov     eax, [ebp+var_28]
0x100108e1  push    eax
0x100108e2  mov     ecx, [eax]
0x100108e4  mov     esi, [ecx+0Ch]
0x100108e7  mov     ecx, esi; this
0x100108e9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100108ef  call    esi
0x100108f1  mov     [ebp+ConnectionHandle], eax
0x100108f4  mov     eax, [ebp+var_28]
0x100108f7  push    eax
0x100108f8  mov     ecx, [eax]
0x100108fa  mov     esi, [ecx+8]
0x100108fd  mov     ecx, esi; this
0x100108ff  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10010905  call    esi
0x10010907  cmp     [ebp+ConnectionHandle], 0
0x1001090b  jz      loc_10010A28
0x10010911  mov     ecx, dword ptr [ebp+var_24]
0x10010914  mov     eax, [ecx]
0x10010916  mov     esi, [eax]
0x10010918  lea     eax, [ebp+var_20]
0x1001091b  push    eax
0x1001091c  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x10010921  push    ecx
0x10010922  mov     ecx, esi; this
0x10010924  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001092a  call    esi
0x1001092c  test    eax, eax
0x1001092e  js      loc_10010A28
0x10010934  mov     eax, [edi+14h]
0x10010937  mov     [ebp+AllocatorFraming.Frames], eax
0x1001093a  mov     eax, [edi+18h]
0x1001093d  mov     [ebp+AllocatorFraming.FrameSize], eax
0x10010940  mov     eax, [edi+1Ch]
0x10010943  dec     eax
0x10010944  mov     dword ptr [ebp+AllocatorFraming], 2
0x1001094b  mov     dword ptr [ebp+AllocatorFraming.10h], eax
0x1001094e  xor     eax, eax
0x10010950  cmp     dword ptr [edi+0C4h], 1
0x10010957  setz    al
0x1001095a  mov     [ebp+AllocatorFraming.PoolType], eax
0x1001095d  mov     eax, _WPP_GLOBAL_Control
0x10010962  cmp     eax, offset _WPP_GLOBAL_Control
0x10010967  jz      short loc_100109B8
0x10010969  cmp     byte ptr [eax+19h], 2
0x1001096d  jb      short loc_100109B8
0x1001096f  mov     eax, [ebp+var_20]
0x10010972  push    eax
0x10010973  mov     ecx, [eax]
0x10010975  mov     esi, [ecx+30h]
0x10010978  mov     ecx, esi; this
0x1001097a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10010980  call    esi
0x10010982  mov     edi, eax
0x10010984  mov     eax, [ebp+var_20]
0x10010987  push    eax
0x10010988  mov     ecx, [eax]
0x1001098a  mov     esi, [ecx+34h]
0x1001098d  mov     ecx, esi; this
0x1001098f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10010995  call    esi
0x10010997  push    dword ptr [ebp+AllocatorFraming]; char
0x1001099a  push    dword ptr [ebp+AllocatorFraming.10h]; char
0x1001099d  push    [ebp+AllocatorFraming.FrameSize]; char
0x100109a0  push    [ebp+AllocatorFraming.Frames]; char
0x100109a3  push    dword ptr [ebp+var_24]; char
0x100109a6  push    edi; int
0x100109a7  push    eax; int
0x100109a8  mov     eax, _WPP_GLOBAL_Control
0x100109ad  push    dword ptr [eax+14h]
0x100109b0  push    dword ptr [eax+10h]; LoggerHandle
0x100109b3  call    _WPP_SF_SSqdddD@44; WPP_SF_SSqdddD(x,x,x,x,x,x,x,x,x,x,x)
0x100109b8  push    ebx; AllocatorHandle
0x100109b9  lea     eax, [ebp+AllocatorFraming]
0x100109bc  push    eax; AllocatorFraming
0x100109bd  push    [ebp+ConnectionHandle]; ConnectionHandle
0x100109c0  call    ds:__imp__KsCreateAllocator@12; KsCreateAllocator(x,x,x)
0x100109c6  test    eax, eax
0x100109c8  jz      short loc_10010A0D
0x100109ca  call    ds:__imp__GetLastError@0; GetLastError()
0x100109d0  mov     edx, eax
0x100109d2  mov     dword ptr [ebx], 0
0x100109d8  mov     ecx, _WPP_GLOBAL_Control
0x100109de  cmp     ecx, offset _WPP_GLOBAL_Control
0x100109e4  jz      short loc_10010A0D
0x100109e6  cmp     byte ptr [ecx+19h], 2
0x100109ea  jb      short loc_10010A0D
0x100109ec  movzx   eax, dx
0x100109ef  or      eax, 80070000h
0x100109f4  test    edx, edx
0x100109f6  cmovle  eax, edx
0x100109f9  mov     edx, offset _WPP_fe7a9118b06232fec4bd8b1a4538b614_Traceguids; MessageGuid
0x100109fe  push    eax; char
0x100109ff  push    dword ptr [ecx+14h]
0x10010a02  push    dword ptr [ecx+10h]; LoggerHandle
0x10010a05  push    0Dh
0x10010a07  pop     ecx; MessageNumber
0x10010a08  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10010a0d  mov     edx, [ebp+var_20]
0x10010a10  test    edx, edx
0x10010a12  jz      short loc_10010A24
0x10010a14  mov     ecx, [edx]
0x10010a16  push    edx
0x10010a17  mov     esi, [ecx+8]
0x10010a1a  mov     ecx, esi; this
0x10010a1c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10010a22  call    esi
0x10010a24  mov     eax, [ebx]
0x10010a26  jmp     short loc_10010A2A
0x10010a28  xor     eax, eax
0x10010a2a  mov     ecx, [ebp+var_4]
0x10010a2d  pop     edi
0x10010a2e  pop     esi
0x10010a2f  xor     ecx, ebp; StackCookie
0x10010a31  pop     ebx
0x10010a32  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10010a37  leave
0x10010a38  retn    8
```
