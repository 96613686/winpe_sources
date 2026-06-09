# CVPVBIInterfaceHandler::NotifyThreadProc(void)

- ea: `0x100369b0`
- end: `0x10036ba0`
- name: `?NotifyThreadProc@CVPVBIInterfaceHandler@@UAEKXZ`
- size: `496`
- prototype: `unsigned int __thiscall(CVPVBIInterfaceHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x100063f1`
- `0x1002d510`
- `0x100369b0`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x10036a18`
- `KERNEL32!WaitForMultipleObjects` at `0x10036a18`
- `KERNEL32!ResetEvent` at `0x10036a46`
- `KERNEL32!ResetEvent` at `0x10036a46`

## pseudocode

```c
unsigned int __thiscall CVPVBIInterfaceHandler::NotifyThreadProc(CVPVBIInterfaceHandler *this)
{
  PVOID *v2; // edx
  DWORD v3; // eax
  HRESULT (__stdcall *ConnectedTo)(IPin *, IPin **); // ecx
  int v6; // [esp+18h] [ebp-10h] BYREF
  _DWORD **v7; // [esp+1Ch] [ebp-Ch] BYREF
  HANDLE Handles[2]; // [esp+20h] [ebp-8h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    WPP_SF_(0x24u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  Handles[0] = this->m_NotifyEventHandle;
  Handles[1] = this->m_EndEventHandle;
LABEL_4:
  if ( v2 != &WPP_GLOBAL_Control )
    WPP_SF_(0x25u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)v2 + 2));
  while ( 1 )
  {
    v3 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( v3 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_(0x26u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
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
             &_GUID_ec529b01_1a1f_11d1_bad9_00609744111a,
             &v6) < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(0x28u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_(0x27u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
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
      WPP_SF_(0x29u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
      goto LABEL_22;
    }
  }
  if ( v3 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(0x2Au, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    return 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_(0x2Bu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    return 0;
  }
}

```

## disassembly

```asm
0x100369b0  mov     edi, edi
0x100369b2  push    ebp
0x100369b3  mov     ebp, esp
0x100369b5  and     esp, 0FFFFFFF8h
0x100369b8  sub     esp, 14h
0x100369bb  push    ebx
0x100369bc  push    esi
0x100369bd  push    edi
0x100369be  mov     edi, ecx
0x100369c0  mov     edx, _WPP_GLOBAL_Control
0x100369c6  mov     ebx, offset _WPP_GLOBAL_Control
0x100369cb  cmp     edx, ebx
0x100369cd  jz      short loc_100369E8
0x100369cf  push    dword ptr [edx+14h]
0x100369d2  push    dword ptr [edx+10h]; LoggerHandle
0x100369d5  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x100369da  push    24h ; '$'
0x100369dc  pop     ecx; MessageNumber
0x100369dd  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x100369e2  mov     edx, _WPP_GLOBAL_Control
0x100369e8  mov     eax, [edi+2Ch]
0x100369eb  mov     [esp+20h+Handles], eax
0x100369ef  mov     eax, [edi+14h]
0x100369f2  mov     [esp+20h+var_4], eax
0x100369f6  cmp     edx, ebx
0x100369f8  jz      short loc_10036A0D
0x100369fa  push    dword ptr [edx+14h]
0x100369fd  push    dword ptr [edx+10h]; LoggerHandle
0x10036a00  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036a05  push    25h ; '%'
0x10036a07  pop     ecx; MessageNumber
0x10036a08  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036a0d  push    0FFFFFFFFh; dwMilliseconds
0x10036a0f  push    0; bWaitAll
0x10036a11  lea     eax, [esp+28h+Handles]
0x10036a15  push    eax; lpHandles
0x10036a16  push    2; nCount
0x10036a18  call    ds:__imp__WaitForMultipleObjects@16; WaitForMultipleObjects(x,x,x,x)
0x10036a1e  sub     eax, 0
0x10036a21  jnz     loc_10036B49
0x10036a27  mov     eax, _WPP_GLOBAL_Control
0x10036a2c  cmp     eax, ebx
0x10036a2e  jz      short loc_10036A43
0x10036a30  push    dword ptr [eax+14h]
0x10036a33  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036a38  push    dword ptr [eax+10h]; LoggerHandle
0x10036a3b  push    26h ; '&'
0x10036a3d  pop     ecx; MessageNumber
0x10036a3e  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036a43  push    dword ptr [edi+2Ch]; hEvent
0x10036a46  call    ds:__imp__ResetEvent@4; ResetEvent(x)
0x10036a4c  mov     ecx, [edi+18h]
0x10036a4f  mov     eax, [ecx]
0x10036a51  mov     esi, [eax+18h]
0x10036a54  lea     eax, [esp+20h+var_C]
0x10036a58  push    eax
0x10036a59  push    ecx
0x10036a5a  mov     ecx, esi; this
0x10036a5c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036a62  call    esi
0x10036a64  test    eax, eax
0x10036a66  js      loc_10036B13
0x10036a6c  mov     ecx, [esp+20h+var_C]
0x10036a70  test    ecx, ecx
0x10036a72  jz      loc_10036B13
0x10036a78  mov     eax, [ecx]
0x10036a7a  mov     esi, [eax]
0x10036a7c  lea     eax, [esp+20h+var_10]
0x10036a80  push    eax
0x10036a81  push    offset __GUID_ec529b01_1a1f_11d1_bad9_00609744111a
0x10036a86  push    ecx
0x10036a87  mov     ecx, esi; this
0x10036a89  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036a8f  call    esi
0x10036a91  test    eax, eax
0x10036a93  js      short loc_10036ADB
0x10036a95  mov     eax, _WPP_GLOBAL_Control
0x10036a9a  cmp     eax, ebx
0x10036a9c  jz      short loc_10036AB1
0x10036a9e  push    dword ptr [eax+14h]
0x10036aa1  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036aa6  push    dword ptr [eax+10h]; LoggerHandle
0x10036aa9  push    27h ; '''
0x10036aab  pop     ecx; MessageNumber
0x10036aac  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036ab1  mov     eax, [esp+20h+var_10]
0x10036ab5  push    eax
0x10036ab6  mov     ecx, [eax]
0x10036ab8  mov     esi, [ecx+0Ch]
0x10036abb  mov     ecx, esi; this
0x10036abd  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036ac3  call    esi
0x10036ac5  mov     eax, [esp+20h+var_10]
0x10036ac9  push    eax
0x10036aca  mov     ecx, [eax]
0x10036acc  mov     esi, [ecx+8]
0x10036acf  mov     ecx, esi; this
0x10036ad1  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036ad7  call    esi
0x10036ad9  jmp     short loc_10036AFD
0x10036adb  mov     eax, _WPP_GLOBAL_Control
0x10036ae0  cmp     eax, ebx
0x10036ae2  jz      short loc_10036AFD
0x10036ae4  cmp     byte ptr [eax+19h], 2
0x10036ae8  jb      short loc_10036AFD
0x10036aea  push    dword ptr [eax+14h]
0x10036aed  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036af2  push    dword ptr [eax+10h]; LoggerHandle
0x10036af5  push    28h ; '('
0x10036af7  pop     ecx; MessageNumber
0x10036af8  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036afd  mov     eax, [esp+20h+var_C]
0x10036b01  push    eax
0x10036b02  mov     ecx, [eax]
0x10036b04  mov     esi, [ecx+8]
0x10036b07  mov     ecx, esi; this
0x10036b09  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10036b0f  call    esi
0x10036b11  jmp     short loc_10036B3E
0x10036b13  mov     edx, _WPP_GLOBAL_Control
0x10036b19  cmp     edx, ebx
0x10036b1b  jz      loc_10036A0D
0x10036b21  cmp     byte ptr [edx+19h], 2
0x10036b25  jb      loc_100369F6
0x10036b2b  push    dword ptr [edx+14h]
0x10036b2e  push    dword ptr [edx+10h]; LoggerHandle
0x10036b31  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036b36  push    29h ; ')'
0x10036b38  pop     ecx; MessageNumber
0x10036b39  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036b3e  mov     edx, _WPP_GLOBAL_Control
0x10036b44  jmp     loc_100369F6
0x10036b49  sub     eax, 1
0x10036b4c  jz      short loc_10036B74
0x10036b4e  mov     eax, _WPP_GLOBAL_Control
0x10036b53  cmp     eax, ebx
0x10036b55  jz      short loc_10036B70
0x10036b57  cmp     byte ptr [eax+19h], 1
0x10036b5b  jb      short loc_10036B70
0x10036b5d  push    dword ptr [eax+14h]
0x10036b60  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036b65  push    dword ptr [eax+10h]; LoggerHandle
0x10036b68  push    2Bh ; '+'
0x10036b6a  pop     ecx; MessageNumber
0x10036b6b  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036b70  xor     eax, eax
0x10036b72  jmp     short loc_10036B99
0x10036b74  mov     eax, _WPP_GLOBAL_Control
0x10036b79  cmp     eax, ebx
0x10036b7b  jz      short loc_10036B96
0x10036b7d  cmp     byte ptr [eax+19h], 2
0x10036b81  jb      short loc_10036B96
0x10036b83  push    dword ptr [eax+14h]
0x10036b86  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036b8b  push    dword ptr [eax+10h]; LoggerHandle
0x10036b8e  push    2Ah ; '*'
0x10036b90  pop     ecx; MessageNumber
0x10036b91  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x10036b96  xor     eax, eax
0x10036b98  inc     eax
0x10036b99  pop     edi
0x10036b9a  pop     esi
0x10036b9b  pop     ebx
0x10036b9c  mov     esp, ebp
0x10036b9e  pop     ebp
0x10036b9f  retn
```
