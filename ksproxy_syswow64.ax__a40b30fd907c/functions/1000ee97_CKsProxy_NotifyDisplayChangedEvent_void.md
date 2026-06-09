# CKsProxy::NotifyDisplayChangedEvent(void)

- ea: `0x1000ee97`
- end: `0x1000f04e`
- name: `?NotifyDisplayChangedEvent@CKsProxy@@QAEJXZ`
- size: `439`
- prototype: `int __thiscall(CKsProxy *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x10014290`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x1000ecde`
- `0x1000ee97`
- `0x1000f054`
- `0x1002d510`
- `0x10030c17`
- `0x1003a6f2`
- `0x1003b5e4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1000ef36`
- `ole32!CoTaskMemAlloc` at `0x1000ef36`

## pseudocode

```c
int __thiscall CKsProxy::NotifyDisplayChangedEvent(CKsProxy *this)
{
  enum _PinDirection v2; // ecx
  unsigned int v3; // edi
  void *v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  _DWORD *v7; // ecx
  unsigned int i; // ebx
  void *Block; // [esp+Ch] [ebp-Ch] BYREF
  char v11[4]; // [esp+10h] [ebp-8h] BYREF
  char v12[4]; // [esp+14h] [ebp-4h]

  Block = 0;
  *(_DWORD *)v11 = 0;
  if ( this->m_lInProgress )
  {
    CKsProxy::IncrementInProgressCount(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(
        0x20u,
        &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        this->m_lInProgress);
    return 0;
  }
  else
  {
    CKsProxy::IncrementInProgressCount(this);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(
        0x1Fu,
        &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        this->m_lInProgress);
    *(_DWORD *)v12 = CKsProxy::GetConnectedPins(this, v2, (struct IPin ***)&Block, (unsigned int *)v11);
    if ( *(int *)v12 >= 0 )
    {
      v3 = *(_DWORD *)v11;
      if ( *(_DWORD *)v11 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_q(0x21u, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v11[0]);
        v4 = CoTaskMemAlloc(4 * v3);
        *(_DWORD *)v11 = v4;
        if ( v4 )
        {
          memset(v4, 0, 4 * v3);
          v5 = 0;
          if ( v3 )
          {
            v6 = *(_DWORD *)v11;
            v7 = Block;
            do
            {
              *(_DWORD *)v12 = v7[v5];
              *(_DWORD *)(v6 + 4 * v5) = *(_DWORD *)v12;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              {
                WPP_SF_q(
                  0x22u,
                  &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v12[0]);
                v6 = *(_DWORD *)v11;
                v7 = Block;
              }
              ++v5;
            }
            while ( v5 < v3 );
          }
          *(_DWORD *)v12 = CBaseFilter::NotifyEvent(this, 22, *(int *)v11, v3);
          if ( *(int *)v12 >= 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              WPP_SF_(0x24u, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            WPP_SF_(0x23u, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
          }
        }
        for ( i = 0; i < v3; ++i )
          (*(void (__thiscall **)(_DWORD, _DWORD))(**((_DWORD **)Block + i) + 8))(
            *(_DWORD *)(**((_DWORD **)Block + i) + 8),
            *((_DWORD *)Block + i));
      }
    }
    operator delete[](Block);
    return *(_DWORD *)v12;
  }
}

```

## disassembly

```asm
0x1000ee97  mov     edi, edi
0x1000ee99  push    ebp
0x1000ee9a  mov     ebp, esp
0x1000ee9c  and     esp, 0FFFFFFF8h
0x1000ee9f  sub     esp, 0Ch
0x1000eea2  push    ebx
0x1000eea3  push    esi
0x1000eea4  mov     esi, ecx
0x1000eea6  xor     eax, eax
0x1000eea8  push    edi
0x1000eea9  mov     [esp+18h+Block], eax
0x1000eead  mov     dword ptr [esp+18h+var_8], eax
0x1000eeb1  cmp     [esi+184h], eax
0x1000eeb7  jnz     loc_1000F01B
0x1000eebd  call    ?IncrementInProgressCount@CKsProxy@@QAEXXZ; CKsProxy::IncrementInProgressCount(void)
0x1000eec2  mov     eax, _WPP_GLOBAL_Control
0x1000eec7  mov     ebx, offset _WPP_GLOBAL_Control
0x1000eecc  cmp     eax, ebx
0x1000eece  jz      short loc_1000EEE9
0x1000eed0  push    dword ptr [esi+184h]; char
0x1000eed6  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000eedb  push    dword ptr [eax+14h]
0x1000eede  push    dword ptr [eax+10h]; LoggerHandle
0x1000eee1  push    1Fh
0x1000eee3  pop     ecx; MessageNumber
0x1000eee4  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1000eee9  lea     eax, [esp+18h+var_8]
0x1000eeed  push    eax; unsigned int *
0x1000eeee  lea     eax, [esp+1Ch+Block]
0x1000eef2  push    eax; struct IPin ***
0x1000eef3  push    ecx; enum _PinDirection
0x1000eef4  mov     ecx, esi; this
0x1000eef6  call    ?GetConnectedPins@CKsProxy@@QAEJW4_PinDirection@@PAPAPAUIPin@@PAK@Z; CKsProxy::GetConnectedPins(_PinDirection,IPin * * *,ulong *)
0x1000eefb  mov     dword ptr [esp+18h+var_4], eax
0x1000eeff  test    eax, eax
0x1000ef01  js      loc_1000F00B
0x1000ef07  mov     edi, dword ptr [esp+18h+var_8]
0x1000ef0b  test    edi, edi
0x1000ef0d  jz      loc_1000F00B
0x1000ef13  mov     eax, _WPP_GLOBAL_Control
0x1000ef18  cmp     eax, ebx
0x1000ef1a  jz      short loc_1000EF30
0x1000ef1c  push    edi; char
0x1000ef1d  push    dword ptr [eax+14h]
0x1000ef20  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000ef25  push    dword ptr [eax+10h]; LoggerHandle
0x1000ef28  push    21h ; '!'
0x1000ef2a  pop     ecx; MessageNumber
0x1000ef2b  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1000ef30  mov     ebx, edi
0x1000ef32  shl     ebx, 2
0x1000ef35  push    ebx; cb
0x1000ef36  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1000ef3c  mov     dword ptr [esp+18h+var_8], eax
0x1000ef40  test    eax, eax
0x1000ef42  jz      loc_1000EFE9
0x1000ef48  push    ebx; Size
0x1000ef49  push    0; Val
0x1000ef4b  push    eax; void *
0x1000ef4c  call    _memset
0x1000ef51  add     esp, 0Ch
0x1000ef54  xor     ebx, ebx
0x1000ef56  test    edi, edi
0x1000ef58  jz      short loc_1000EF9E
0x1000ef5a  mov     eax, dword ptr [esp+18h+var_8]
0x1000ef5e  mov     ecx, [esp+18h+Block]
0x1000ef62  mov     edx, [ecx+ebx*4]
0x1000ef65  mov     dword ptr [esp+18h+var_4], edx
0x1000ef69  mov     [eax+ebx*4], edx
0x1000ef6c  mov     edx, _WPP_GLOBAL_Control
0x1000ef72  cmp     edx, offset _WPP_GLOBAL_Control
0x1000ef78  jz      short loc_1000EF99
0x1000ef7a  push    dword ptr [esp+18h+var_4]; char
0x1000ef7e  push    dword ptr [edx+14h]
0x1000ef81  push    dword ptr [edx+10h]; LoggerHandle
0x1000ef84  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000ef89  push    22h ; '"'
0x1000ef8b  pop     ecx; MessageNumber
0x1000ef8c  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1000ef91  mov     eax, dword ptr [esp+18h+var_8]
0x1000ef95  mov     ecx, [esp+18h+Block]
0x1000ef99  inc     ebx
0x1000ef9a  cmp     ebx, edi
0x1000ef9c  jb      short loc_1000EF62
0x1000ef9e  push    edi; int
0x1000ef9f  push    dword ptr [esp+1Ch+var_8]; int
0x1000efa3  mov     ecx, esi; this
0x1000efa5  push    16h; int
0x1000efa7  call    ?NotifyEvent@CBaseFilter@@QAEJJJJ@Z; CBaseFilter::NotifyEvent(long,long,long)
0x1000efac  mov     dword ptr [esp+18h+var_4], eax
0x1000efb0  test    eax, eax
0x1000efb2  jns     short loc_1000EFCA
0x1000efb4  mov     eax, _WPP_GLOBAL_Control
0x1000efb9  cmp     eax, offset _WPP_GLOBAL_Control
0x1000efbe  jz      short loc_1000EFE9
0x1000efc0  push    dword ptr [eax+14h]
0x1000efc3  push    dword ptr [eax+10h]
0x1000efc6  push    23h ; '#'
0x1000efc8  jmp     short loc_1000EFDE
0x1000efca  mov     eax, _WPP_GLOBAL_Control
0x1000efcf  cmp     eax, offset _WPP_GLOBAL_Control
0x1000efd4  jz      short loc_1000EFE9
0x1000efd6  push    dword ptr [eax+14h]
0x1000efd9  push    dword ptr [eax+10h]; LoggerHandle
0x1000efdc  push    24h ; '$'
0x1000efde  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000efe3  pop     ecx; MessageNumber
0x1000efe4  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1000efe9  xor     ebx, ebx
0x1000efeb  test    edi, edi
0x1000efed  jz      short loc_1000F00B
0x1000efef  mov     eax, [esp+18h+Block]
0x1000eff3  mov     eax, [eax+ebx*4]
0x1000eff6  push    eax
0x1000eff7  mov     ecx, [eax]
0x1000eff9  mov     esi, [ecx+8]
0x1000effc  mov     ecx, esi; this
0x1000effe  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000f004  call    esi
0x1000f006  inc     ebx
0x1000f007  cmp     ebx, edi
0x1000f009  jb      short loc_1000EFEF
0x1000f00b  push    [esp+18h+Block]; Block
0x1000f00f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1000f014  mov     eax, dword ptr [esp+1Ch+var_4]
0x1000f018  pop     ecx
0x1000f019  jmp     short loc_1000F047
0x1000f01b  call    ?IncrementInProgressCount@CKsProxy@@QAEXXZ; CKsProxy::IncrementInProgressCount(void)
0x1000f020  mov     eax, _WPP_GLOBAL_Control
0x1000f025  cmp     eax, offset _WPP_GLOBAL_Control
0x1000f02a  jz      short loc_1000F045
0x1000f02c  push    dword ptr [esi+184h]; char
0x1000f032  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000f037  push    dword ptr [eax+14h]
0x1000f03a  push    dword ptr [eax+10h]; LoggerHandle
0x1000f03d  push    20h ; ' '
0x1000f03f  pop     ecx; MessageNumber
0x1000f040  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1000f045  xor     eax, eax
0x1000f047  pop     edi
0x1000f048  pop     esi
0x1000f049  pop     ebx
0x1000f04a  mov     esp, ebp
0x1000f04c  pop     ebp
0x1000f04d  retn
```
