# CVPVideoInterfaceHandler::NotifyThreadProc(void)

- ea: `0x100364d0`
- end: `0x100366d0`
- name: `?NotifyThreadProc@CVPVideoInterfaceHandler@@UAEKXZ`
- size: `512`
- prototype: `unsigned int __thiscall(CVPVideoInterfaceHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x100063f1`
- `0x1002d510`
- `0x100364d0`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x10036548`
- `KERNEL32!WaitForMultipleObjects` at `0x10036548`
- `KERNEL32!ResetEvent` at `0x10036576`
- `KERNEL32!ResetEvent` at `0x10036576`

## pseudocode

```c
unsigned int __thiscall CVPVideoInterfaceHandler::NotifyThreadProc(CVPVideoInterfaceHandler *this)
{
  PVOID *v2; // edx
  DWORD v3; // eax
  HRESULT (__stdcall *ConnectedTo)(IPin *, IPin **); // ecx
  int v6; // [esp+18h] [ebp-10h] BYREF
  _DWORD **v7; // [esp+1Ch] [ebp-Ch] BYREF
  HANDLE Handles[2]; // [esp+20h] [ebp-8h] BYREF

  v6 = 0;
  v7 = 0;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    WPP_SF_(0x17u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  Handles[0] = this->m_NotifyEventHandle;
  Handles[1] = this->m_EndEventHandle;
LABEL_4:
  if ( v2 != &WPP_GLOBAL_Control )
    WPP_SF_(0x18u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)v2 + 2));
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v3 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_(0x19u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    ResetEvent(this->m_NotifyEventHandle);
    ConnectedTo = this->m_Pin->ConnectedTo;
    if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IPin *, IPin **), IPin *, _DWORD ***))ConnectedTo)(
           ConnectedTo,
           this->m_Pin,
           &v7) >= 0
      && v7 )
    {
      if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v7)(
             **v7,
             v7,
             &_GUID_c76794a1_d6c5_11d0_9e69_00c04fd7c15b,
             &v6) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(0x1Bu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(0x1Au, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v6 + 12))(*(_DWORD *)(*(_DWORD *)v6 + 12), v6);
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v6 + 8))(*(_DWORD *)(*(_DWORD *)v6 + 8), v6);
      }
      ((void (__thiscall *)(_DWORD, _DWORD **))(*v7)[2])((*v7)[2], v7);
LABEL_22:
      v2 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_4;
    }
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_4;
      WPP_SF_(0x1Cu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
      goto LABEL_22;
    }
  }
  if ( v3 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(0x1Du, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_(0x1Eu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    return 0;
  }
}

```

## disassembly

```asm
0x100364d0  mov     edi, edi
0x100364d2  push    ebp
0x100364d3  mov     ebp, esp
0x100364d5  and     esp, 0FFFFFFF8h
0x100364d8  sub     esp, 14h
0x100364db  push    ebx
0x100364dc  push    esi
0x100364dd  push    edi
0x100364de  mov     edi, ecx
0x100364e0  mov     [esp+20h+var_10], 0
0x100364e8  mov     [esp+20h+var_C], 0
0x100364f0  mov     edx, _WPP_GLOBAL_Control
0x100364f6  mov     ebx, offset _WPP_GLOBAL_Control
0x100364fb  cmp     edx, ebx
0x100364fd  jz      short loc_10036518
0x100364ff  push    dword ptr [edx+14h]
0x10036502  push    dword ptr [edx+10h]; LoggerHandle
0x10036505  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x1003650a  push    17h
0x1003650c  pop     ecx; MessageNumber
0x1003650d  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036512  mov     edx, _WPP_GLOBAL_Control
0x10036518  mov     eax, [edi+2Ch]
0x1003651b  mov     [esp+20h+Handles], eax
0x1003651f  mov     eax, [edi+14h]
0x10036522  mov     [esp+20h+var_4], eax
0x10036526  cmp     edx, ebx
0x10036528  jz      short loc_1003653D
0x1003652a  push    dword ptr [edx+14h]
0x1003652d  push    dword ptr [edx+10h]; LoggerHandle
0x10036530  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036535  push    18h
0x10036537  pop     ecx; MessageNumber
0x10036538  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1003653d  push    0FFFFFFFFh; dwMilliseconds
0x1003653f  push    0; bWaitAll
0x10036541  lea     eax, [esp+28h+Handles]
0x10036545  push    eax; lpHandles
0x10036546  push    2; nCount
0x10036548  call    ds:__imp__WaitForMultipleObjects@16; WaitForMultipleObjects(x,x,x,x)
0x1003654e  sub     eax, 0
0x10036551  jnz     loc_10036679
0x10036557  mov     eax, _WPP_GLOBAL_Control
0x1003655c  cmp     eax, ebx
0x1003655e  jz      short loc_10036573
0x10036560  push    dword ptr [eax+14h]
0x10036563  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036568  push    dword ptr [eax+10h]; LoggerHandle
0x1003656b  push    19h
0x1003656d  pop     ecx; MessageNumber
0x1003656e  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036573  push    dword ptr [edi+2Ch]; hEvent
0x10036576  call    ds:__imp__ResetEvent@4; ResetEvent(x)
0x1003657c  mov     ecx, [edi+18h]
0x1003657f  mov     eax, [ecx]
0x10036581  mov     esi, [eax+18h]
0x10036584  lea     eax, [esp+20h+var_C]
0x10036588  push    eax
0x10036589  push    ecx
0x1003658a  mov     ecx, esi; this
0x1003658c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036592  call    esi
0x10036594  test    eax, eax
0x10036596  js      loc_10036643
0x1003659c  mov     ecx, [esp+20h+var_C]
0x100365a0  test    ecx, ecx
0x100365a2  jz      loc_10036643
0x100365a8  mov     eax, [ecx]
0x100365aa  mov     esi, [eax]
0x100365ac  lea     eax, [esp+20h+var_10]
0x100365b0  push    eax
0x100365b1  push    offset __GUID_c76794a1_d6c5_11d0_9e69_00c04fd7c15b
0x100365b6  push    ecx
0x100365b7  mov     ecx, esi; this
0x100365b9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100365bf  call    esi
0x100365c1  test    eax, eax
0x100365c3  js      short loc_1003660B
0x100365c5  mov     eax, _WPP_GLOBAL_Control
0x100365ca  cmp     eax, ebx
0x100365cc  jz      short loc_100365E1
0x100365ce  push    dword ptr [eax+14h]
0x100365d1  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x100365d6  push    dword ptr [eax+10h]; LoggerHandle
0x100365d9  push    1Ah
0x100365db  pop     ecx; MessageNumber
0x100365dc  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x100365e1  mov     eax, [esp+20h+var_10]
0x100365e5  push    eax
0x100365e6  mov     ecx, [eax]
0x100365e8  mov     esi, [ecx+0Ch]
0x100365eb  mov     ecx, esi; this
0x100365ed  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100365f3  call    esi
0x100365f5  mov     eax, [esp+20h+var_10]
0x100365f9  push    eax
0x100365fa  mov     ecx, [eax]
0x100365fc  mov     esi, [ecx+8]
0x100365ff  mov     ecx, esi; this
0x10036601  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036607  call    esi
0x10036609  jmp     short loc_1003662D
0x1003660b  mov     eax, _WPP_GLOBAL_Control
0x10036610  cmp     eax, ebx
0x10036612  jz      short loc_1003662D
0x10036614  cmp     byte ptr [eax+19h], 2
0x10036618  jb      short loc_1003662D
0x1003661a  push    dword ptr [eax+14h]
0x1003661d  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036622  push    dword ptr [eax+10h]; LoggerHandle
0x10036625  push    1Bh
0x10036627  pop     ecx; MessageNumber
0x10036628  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1003662d  mov     eax, [esp+20h+var_C]
0x10036631  push    eax
0x10036632  mov     ecx, [eax]
0x10036634  mov     esi, [ecx+8]
0x10036637  mov     ecx, esi; this
0x10036639  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003663f  call    esi
0x10036641  jmp     short loc_1003666E
0x10036643  mov     edx, _WPP_GLOBAL_Control
0x10036649  cmp     edx, ebx
0x1003664b  jz      loc_1003653D
0x10036651  cmp     byte ptr [edx+19h], 2
0x10036655  jb      loc_10036526
0x1003665b  push    dword ptr [edx+14h]
0x1003665e  push    dword ptr [edx+10h]; LoggerHandle
0x10036661  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036666  push    1Ch
0x10036668  pop     ecx; MessageNumber
0x10036669  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1003666e  mov     edx, _WPP_GLOBAL_Control
0x10036674  jmp     loc_10036526
0x10036679  sub     eax, 1
0x1003667c  jz      short loc_100366A4
0x1003667e  mov     eax, _WPP_GLOBAL_Control
0x10036683  cmp     eax, ebx
0x10036685  jz      short loc_100366A0
0x10036687  cmp     byte ptr [eax+19h], 1
0x1003668b  jb      short loc_100366A0
0x1003668d  push    dword ptr [eax+14h]
0x10036690  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036695  push    dword ptr [eax+10h]; LoggerHandle
0x10036698  push    1Eh
0x1003669a  pop     ecx; MessageNumber
0x1003669b  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x100366a0  xor     eax, eax
0x100366a2  jmp     short loc_100366C9
0x100366a4  mov     eax, _WPP_GLOBAL_Control
0x100366a9  cmp     eax, ebx
0x100366ab  jz      short loc_100366C6
0x100366ad  cmp     byte ptr [eax+19h], 2
0x100366b1  jb      short loc_100366C6
0x100366b3  push    dword ptr [eax+14h]
0x100366b6  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x100366bb  push    dword ptr [eax+10h]; LoggerHandle
0x100366be  push    1Dh
0x100366c0  pop     ecx; MessageNumber
0x100366c1  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x100366c6  xor     eax, eax
0x100366c8  inc     eax
0x100366c9  pop     edi
0x100366ca  pop     esi
0x100366cb  pop     ebx
0x100366cc  mov     esp, ebp
0x100366ce  pop     ebp
0x100366cf  retn
```
