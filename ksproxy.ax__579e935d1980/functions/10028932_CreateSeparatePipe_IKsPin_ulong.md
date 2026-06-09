# CreateSeparatePipe(IKsPin *,ulong)

- ea: `0x10028932`
- end: `0x10028acb`
- name: `?CreateSeparatePipe@@YGJPAUIKsPin@@K@Z`
- size: `409`
- prototype: `int __cdecl(struct IKsPin *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x10012740`
- `0x10023d3c`
- `0x10024280`

## callees

- `0x1000665f`
- `0x100224d5`
- `0x10027726`
- `0x1002861d`
- `0x10028932`
- `0x10029c63`
- `0x1002d510`

## pseudocode

```c
int __thiscall CreateSeparatePipe(_DWORD **this)
{
  int v2; // ecx
  int PipeBasedOnOnePin; // esi
  int v4; // ecx
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ecx
  struct IKsPin *v8; // ecx
  struct _GUID v10; // [esp-18h] [ebp-38h]
  int v11; // [esp+0h] [ebp-20h]
  unsigned int v12; // [esp+0h] [ebp-20h]
  unsigned int *v13; // [esp+0h] [ebp-20h]
  unsigned int v14; // [esp+0h] [ebp-20h]
  struct IKsPin **v15; // [esp+4h] [ebp-1Ch]
  struct IKsPin *v16; // [esp+4h] [ebp-1Ch]
  int v17; // [esp+4h] [ebp-1Ch]
  unsigned int v18; // [esp+4h] [ebp-1Ch]
  int v19; // [esp+14h] [ebp-Ch] BYREF
  struct IKsAllocatorEx v20; // [esp+18h] [ebp-8h] BYREF
  int v21; // [esp+1Ch] [ebp-4h] BYREF

  v20.__vftable = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(0x96u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), (char)this);
  FindConnectedPinOnPipe(0, &v20, v11, v15);
  if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**this)(
         **this,
         this,
         &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
         &v21) >= 0 )
  {
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v21 + 8))(*(_DWORD *)(*(_DWORD *)v21 + 8), v21);
    v2 = v21;
  }
  else
  {
    v2 = 0;
    v21 = 0;
  }
  (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v2 + 24))(*(_DWORD *)(*(_DWORD *)v2 + 24), v2, 0);
  (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v21 + 28))(*(_DWORD *)(*(_DWORD *)v21 + 28), v21, 0);
  ((void (__thiscall *)(_DWORD, _DWORD **, _DWORD))(*this)[11])((*this)[11], this, 0);
  PipeBasedOnOnePin = MakePipeBasedOnOnePin(0, v12, v16);
  if ( v20.__vftable )
  {
    if ( (*(int (__thiscall **)(_DWORD, IKsAllocatorEx_vtbl *, GUID *, int *))v20.QueryInterface)(
           *(_DWORD *)v20.QueryInterface,
           v20.__vftable,
           &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
           &v19) >= 0 )
    {
      (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v19 + 8))(*(_DWORD *)(*(_DWORD *)v19 + 8), v19);
      v4 = v19;
    }
    else
    {
      v4 = 0;
      v19 = 0;
    }
    v5 = (*(int (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)v4 + 24))(*(_DWORD *)(*(_DWORD *)v4 + 24), v4, 0);
    v6 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v5 + 28))(*(_DWORD *)(*(_DWORD *)v5 + 28), v5);
    *(_DWORD *)v10.Data4 = *(_DWORD *)(v6 + 16);
    *(_QWORD *)&v10.Data1 = v7 | 0x100000000LL;
    *(_DWORD *)&v10.Data4[4] = *(_DWORD *)(v6 + 20);
    AssignPipeAllocatorHandler(
      (struct IKsPin *)2,
      0,
      v10,
      *(_DWORD *)(v6 + 24),
      *(struct IKsPin ***)(v6 + 28),
      v13,
      v17);
    PipeBasedOnOnePin = ResolvePipeDimensions(v8, v14, v18);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(
      0x97u,
      &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      PipeBasedOnOnePin);
  return PipeBasedOnOnePin;
}

```

## disassembly

```asm
0x10028932  mov     edi, edi
0x10028934  push    ebp
0x10028935  mov     ebp, esp
0x10028937  sub     esp, 14h
0x1002893a  push    ebx
0x1002893b  push    esi; unsigned int
0x1002893c  mov     ebx, edx
0x1002893e  mov     [ebp+var_8.__vftable], 0
0x10028945  push    edi; unsigned int
0x10028946  mov     [ebp+var_10], ebx
0x10028949  mov     edi, ecx
0x1002894b  mov     eax, _WPP_GLOBAL_Control
0x10028950  cmp     eax, offset _WPP_GLOBAL_Control
0x10028955  jz      short loc_10028973
0x10028957  cmp     byte ptr [eax+19h], 2
0x1002895b  jb      short loc_10028973
0x1002895d  push    edi; char
0x1002895e  push    dword ptr [eax+14h]
0x10028961  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x10028966  mov     ecx, 96h; MessageNumber
0x1002896b  push    dword ptr [eax+10h]; LoggerHandle
0x1002896e  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10028973  lea     eax, [ebp+var_8]
0x10028976  xor     edx, edx
0x10028978  push    eax; struct IKsAllocatorEx *
0x10028979  push    0; struct IKsPin *
0x1002897b  mov     ecx, edi
0x1002897d  call    ?FindConnectedPinOnPipe@@YGHPAUIKsPin@@PAUIKsAllocatorEx@@HPAPAU1@@Z; FindConnectedPinOnPipe(IKsPin *,IKsAllocatorEx *,int,IKsPin * *)
0x10028982  mov     eax, [edi]
0x10028984  mov     esi, [eax]
0x10028986  lea     eax, [ebp+var_4]
0x10028989  push    eax
0x1002898a  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x1002898f  push    edi
0x10028990  mov     ecx, esi; this
0x10028992  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10028998  call    esi
0x1002899a  test    eax, eax
0x1002899c  jns     short loc_100289A5
0x1002899e  xor     ecx, ecx
0x100289a0  mov     [ebp+var_4], ecx
0x100289a3  jmp     short loc_100289BB
0x100289a5  mov     eax, [ebp+var_4]
0x100289a8  push    eax
0x100289a9  mov     ecx, [eax]
0x100289ab  mov     esi, [ecx+8]
0x100289ae  mov     ecx, esi; this
0x100289b0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100289b6  call    esi
0x100289b8  mov     ecx, [ebp+var_4]
0x100289bb  mov     eax, [ecx]
0x100289bd  push    0
0x100289bf  push    ecx
0x100289c0  mov     esi, [eax+18h]
0x100289c3  mov     ecx, esi; this
0x100289c5  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100289cb  call    esi
0x100289cd  mov     eax, [ebp+var_4]
0x100289d0  push    0
0x100289d2  push    eax
0x100289d3  mov     ecx, [eax]
0x100289d5  mov     esi, [ecx+1Ch]
0x100289d8  mov     ecx, esi; this
0x100289da  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100289e0  call    esi
0x100289e2  mov     eax, [edi]
0x100289e4  push    0
0x100289e6  push    edi
0x100289e7  mov     esi, [eax+2Ch]
0x100289ea  mov     ecx, esi; this
0x100289ec  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100289f2  call    esi
0x100289f4  push    0; struct IKsPin *
0x100289f6  mov     edx, ebx
0x100289f8  mov     ecx, edi
0x100289fa  call    ?MakePipeBasedOnOnePin@@YGJPAUIKsPin@@K0@Z; MakePipeBasedOnOnePin(IKsPin *,ulong,IKsPin *)
0x100289ff  mov     ecx, [ebp+var_8.__vftable]
0x10028a02  mov     esi, eax
0x10028a04  test    ecx, ecx
0x10028a06  jz      loc_10028A9C
0x10028a0c  mov     eax, [ecx]
0x10028a0e  mov     esi, [eax]
0x10028a10  lea     eax, [ebp+var_C]
0x10028a13  push    eax
0x10028a14  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x10028a19  push    ecx
0x10028a1a  mov     ecx, esi; this
0x10028a1c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10028a22  call    esi
0x10028a24  test    eax, eax
0x10028a26  jns     short loc_10028A2F
0x10028a28  xor     ecx, ecx
0x10028a2a  mov     [ebp+var_C], ecx
0x10028a2d  jmp     short loc_10028A45
0x10028a2f  mov     eax, [ebp+var_C]
0x10028a32  push    eax
0x10028a33  mov     ecx, [eax]
0x10028a35  mov     esi, [ecx+8]
0x10028a38  mov     ecx, esi; this
0x10028a3a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10028a40  call    esi
0x10028a42  mov     ecx, [ebp+var_C]
0x10028a45  mov     eax, [ecx]
0x10028a47  push    0
0x10028a49  push    ecx; unsigned int
0x10028a4a  mov     esi, [eax+18h]
0x10028a4d  mov     ecx, esi; this
0x10028a4f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10028a55  call    esi
0x10028a57  push    eax; struct IKsPin **
0x10028a58  mov     ecx, [eax]
0x10028a5a  mov     esi, [ecx+1Ch]
0x10028a5d  mov     ecx, esi; this
0x10028a5f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10028a65  call    esi
0x10028a67  xor     ebx, ebx
0x10028a69  cmp     [ebp+var_10], 4
0x10028a6d  setz    bl
0x10028a70  sub     esp, 10h
0x10028a73  mov     edi, esp
0x10028a75  lea     esi, [eax+10h]
0x10028a78  push    1
0x10028a7a  movsd
0x10028a7b  lea     edx, [ebx+4]
0x10028a7e  push    ecx; struct _GUID
0x10028a7f  mov     ecx, [ebp+var_8.__vftable]
0x10028a82  push    0; unsigned int
0x10028a84  movsd
0x10028a85  push    2; struct IKsPin *
0x10028a87  movsd
0x10028a88  movsd
0x10028a89  call    ?AssignPipeAllocatorHandler@@YGHPAUIKsPin@@KU_GUID@@KPAPAU1@PAKH@Z; AssignPipeAllocatorHandler(IKsPin *,ulong,_GUID,ulong,IKsPin * *,ulong *,int)
0x10028a8e  push    ecx; struct IKsPin *
0x10028a8f  mov     ecx, [ebp+var_8.__vftable]
0x10028a92  lea     edx, [ebx+4]
0x10028a95  call    ?ResolvePipeDimensions@@YGJPAUIKsPin@@KK@Z; ResolvePipeDimensions(IKsPin *,ulong,ulong)
0x10028a9a  mov     esi, eax
0x10028a9c  mov     eax, _WPP_GLOBAL_Control
0x10028aa1  cmp     eax, offset _WPP_GLOBAL_Control
0x10028aa6  jz      short loc_10028AC4
0x10028aa8  cmp     byte ptr [eax+19h], 2
0x10028aac  jb      short loc_10028AC4
0x10028aae  push    esi; char
0x10028aaf  push    dword ptr [eax+14h]
0x10028ab2  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x10028ab7  mov     ecx, 97h; MessageNumber
0x10028abc  push    dword ptr [eax+10h]; LoggerHandle
0x10028abf  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10028ac4  pop     edi
0x10028ac5  mov     eax, esi
0x10028ac7  pop     esi
0x10028ac8  pop     ebx
0x10028ac9  leave
0x10028aca  retn
```
