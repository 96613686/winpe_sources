# CD3DSurfaceAllocator::CheckAndUpdateConnectionFormat(CD3DMediaSample *)

- ea: `0x1002dd14`
- end: `0x1002e049`
- name: `?CheckAndUpdateConnectionFormat@CD3DSurfaceAllocator@@QAEJPAVCD3DMediaSample@@@Z`
- size: `821`
- prototype: `int __thiscall(CD3DSurfaceAllocator *__hidden this, struct CD3DMediaSample *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x1002d050`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x1002d510`
- `0x1002dd14`
- `0x1002e04f`
- `0x1003035c`
- `0x1003aba0`
- `0x1003b5e4`

## pseudocode

```c
int __thiscall CD3DSurfaceAllocator::CheckAndUpdateConnectionFormat(
        CD3DSurfaceAllocator *this,
        struct CD3DMediaSample *a2)
{
  int SurfacePitch; // edi
  int v3; // ebx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  _DWORD **v8; // ecx
  char v9; // cl
  unsigned int v10; // edx
  int v11; // ecx
  int v12; // ecx
  _DWORD **v13; // ecx
  int v14; // ebx
  struct _AMMediaType *v16; // [esp+0h] [ebp-74h]
  struct IDirect3DSurface9 *v18; // [esp+18h] [ebp-5Ch] BYREF
  unsigned int v19; // [esp+1Ch] [ebp-58h] BYREF
  _DWORD v20[19]; // [esp+20h] [ebp-54h] BYREF

  SurfacePitch = 0;
  v19 = 0;
  v3 = 0;
  memset(v20, 0, 72);
  v18 = 0;
  if ( !*((_DWORD *)this + 29) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(0x27u, &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    goto LABEL_56;
  }
  SurfacePitch = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD *))(**((_DWORD **)this + 32) + 28))(
                   *(_DWORD *)(**((_DWORD **)this + 32) + 28),
                   *((_DWORD *)this + 32),
                   v20);
  if ( SurfacePitch < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_q(
        0x28u,
        &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids,
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        SurfacePitch);
    goto LABEL_56;
  }
  v4 = 0;
  while ( v20[v4 + 11] == *(&FORMAT_VideoInfo2.Data1 + v4) )
  {
    if ( ++v4 == 4 )
    {
LABEL_16:
      v6 = 0;
      while ( v20[v6 + 11] == *(&FORMAT_VideoInfo.Data1 + v6) )
      {
        if ( ++v6 == 4 )
        {
          v3 = *(_DWORD *)(v20[17] + 52);
          goto LABEL_24;
        }
      }
      v7 = 0;
      while ( v20[v7 + 11] == *(&FORMAT_VideoInfo2.Data1 + v7) )
      {
        if ( ++v7 == 4 )
        {
          v3 = *(_DWORD *)(v20[17] + 76);
          break;
        }
      }
LABEL_24:
      v8 = (_DWORD **)*((_DWORD *)a2 + 21);
      if ( v8 )
      {
        SurfacePitch = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, struct IDirect3DSurface9 **))**v8)(
                         **v8,
                         v8,
                         &IID_IDirect3DSurface9,
                         &v18);
        v9 = SurfacePitch;
        if ( SurfacePitch >= 0 )
        {
          SurfacePitch = CD3DSurfaceAllocator::GetSurfacePitch(this, v18, &v19);
          if ( SurfacePitch >= 0 )
          {
            v10 = v19;
            if ( v19 != v3 )
            {
              v11 = 0;
              while ( v20[v11 + 11] == *(&FORMAT_VideoInfo.Data1 + v11) )
              {
                if ( ++v11 == 4 )
                {
                  *(_DWORD *)(v20[17] + 52) = v19;
                  break;
                }
              }
              v12 = 0;
              while ( v20[v12 + 11] == *(&FORMAT_VideoInfo2.Data1 + v12) )
              {
                if ( ++v12 == 4 )
                {
                  *(_DWORD *)(v20[17] + 76) = v10;
                  break;
                }
              }
              v13 = (_DWORD **)*((_DWORD *)this + 32);
              v19 = 0;
              if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, unsigned int *))**v13)(
                     **v13,
                     v13,
                     &_GUID_e539cd90_a8b4_11d1_8189_00a0c9062802,
                     &v19) < 0 )
              {
                v14 = 0;
              }
              else
              {
                v14 = (*(int (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)v19 + 20))(
                        *(_DWORD *)(*(_DWORD *)v19 + 20),
                        v19);
                (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)v19 + 8))(
                  *(_DWORD *)(*(_DWORD *)v19 + 8),
                  v19);
              }
              SurfacePitch = (*(int (__thiscall **)(_DWORD, int, _DWORD *))(*(_DWORD *)v14 + 44))(
                               *(_DWORD *)(*(_DWORD *)v14 + 44),
                               v14,
                               v20);
              if ( SurfacePitch >= 0 )
              {
                SurfacePitch = (*(int (__thiscall **)(_DWORD, struct CD3DMediaSample *, _DWORD *))(*(_DWORD *)a2 + 56))(
                                 *(_DWORD *)(*(_DWORD *)a2 + 56),
                                 a2,
                                 v20);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                  WPP_SF_q(
                    0x2Du,
                    &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids,
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    SurfacePitch);
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_q(
                  0x2Cu,
                  &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids,
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  SurfacePitch);
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_q(
              0x2Bu,
              &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids,
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              SurfacePitch);
          }
          goto LABEL_56;
        }
      }
      else
      {
        SurfacePitch = -2147418113;
        v9 = -1;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_q(0x2Au, &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v9);
      goto LABEL_56;
    }
  }
  v5 = 0;
  while ( v20[v5 + 11] == *(&FORMAT_VideoInfo.Data1 + v5) )
  {
    if ( ++v5 == 4 )
      goto LABEL_16;
  }
  SurfacePitch = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    WPP_SF_(0x29u, &WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
LABEL_56:
  FreeMediaType(v16);
  if ( v18 )
    ((void (__thiscall *)(ULONG (__stdcall *)(IDirect3DSurface9 *), struct IDirect3DSurface9 *))v18->lpVtbl->Release)(
      v18->lpVtbl->Release,
      v18);
  return SurfacePitch;
}

```

## disassembly

```asm
0x1002dd14  mov     edi, edi
0x1002dd16  push    ebp
0x1002dd17  mov     ebp, esp
0x1002dd19  sub     esp, 68h
0x1002dd1c  mov     eax, ___security_cookie
0x1002dd21  xor     eax, ebp
0x1002dd23  mov     [ebp+var_8], eax
0x1002dd26  mov     eax, [ebp+arg_0]
0x1002dd29  push    ebx
0x1002dd2a  push    esi
0x1002dd2b  push    edi; struct _AMMediaType *
0x1002dd2c  xor     edi, edi
0x1002dd2e  mov     [ebp+var_60], eax
0x1002dd31  push    44h ; 'D'; Size
0x1002dd33  lea     eax, [ebp+var_50]
0x1002dd36  mov     [ebp+var_58], edi
0x1002dd39  mov     esi, ecx
0x1002dd3b  mov     [ebp+var_68], edi
0x1002dd3e  push    edi; Val
0x1002dd3f  push    eax; void *
0x1002dd40  mov     [ebp+var_64], esi
0x1002dd43  mov     ebx, edi
0x1002dd45  mov     [ebp+var_54], edi
0x1002dd48  call    _memset
0x1002dd4d  add     esp, 0Ch
0x1002dd50  mov     [ebp+var_5C], edi
0x1002dd53  cmp     [esi+74h], edi
0x1002dd56  jnz     short loc_1002DD7F
0x1002dd58  mov     eax, _WPP_GLOBAL_Control
0x1002dd5d  cmp     eax, offset _WPP_GLOBAL_Control
0x1002dd62  jz      loc_1002E017
0x1002dd68  cmp     byte ptr [eax+19h], 3
0x1002dd6c  jb      loc_1002E017
0x1002dd72  push    dword ptr [eax+14h]
0x1002dd75  push    dword ptr [eax+10h]
0x1002dd78  push    27h ; '''
0x1002dd7a  jmp     loc_1002E00C
0x1002dd7f  mov     ecx, [esi+80h]
0x1002dd85  mov     eax, [ecx]
0x1002dd87  mov     esi, [eax+1Ch]
0x1002dd8a  lea     eax, [ebp+var_54]
0x1002dd8d  push    eax
0x1002dd8e  push    ecx
0x1002dd8f  mov     ecx, esi; this
0x1002dd91  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002dd97  call    esi
0x1002dd99  mov     edi, eax
0x1002dd9b  test    edi, edi
0x1002dd9d  jns     short loc_1002DDD2
0x1002dd9f  mov     eax, _WPP_GLOBAL_Control
0x1002dda4  cmp     eax, offset _WPP_GLOBAL_Control
0x1002dda9  jz      loc_1002E017
0x1002ddaf  cmp     byte ptr [eax+19h], 3
0x1002ddb3  jb      loc_1002E017
0x1002ddb9  push    edi; char
0x1002ddba  push    dword ptr [eax+14h]
0x1002ddbd  push    dword ptr [eax+10h]; LoggerHandle
0x1002ddc0  push    28h ; '('
0x1002ddc2  mov     edx, offset _WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids; MessageGuid
0x1002ddc7  pop     ecx; MessageNumber
0x1002ddc8  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002ddcd  jmp     loc_1002E017
0x1002ddd2  push    4
0x1002ddd4  lea     esi, [ebp+var_28]
0x1002ddd7  xor     ecx, ecx
0x1002ddd9  pop     edx
0x1002ddda  mov     eax, [esi+ecx*4]
0x1002dddd  mov     edi, offset _FORMAT_VideoInfo2
0x1002dde2  cmp     eax, [edi+ecx*4]
0x1002dde5  mov     edi, offset _FORMAT_VideoInfo
0x1002ddea  jnz     short loc_1002DDF3
0x1002ddec  inc     ecx
0x1002dded  cmp     ecx, edx
0x1002ddef  jnz     short loc_1002DDDA
0x1002ddf1  jmp     short loc_1002DE09
0x1002ddf3  lea     esi, [ebp+var_28]
0x1002ddf6  xor     ecx, ecx
0x1002ddf8  mov     eax, [esi+ecx*4]
0x1002ddfb  cmp     eax, [edi+ecx*4]
0x1002ddfe  jnz     loc_1002DFF0
0x1002de04  inc     ecx
0x1002de05  cmp     ecx, edx
0x1002de07  jnz     short loc_1002DDF8
0x1002de09  lea     esi, [ebp+var_28]
0x1002de0c  xor     ecx, ecx
0x1002de0e  mov     eax, [esi+ecx*4]
0x1002de11  cmp     eax, [edi+ecx*4]
0x1002de14  jnz     short loc_1002DE23
0x1002de16  inc     ecx
0x1002de17  cmp     ecx, edx
0x1002de19  jnz     short loc_1002DE0E
0x1002de1b  mov     eax, [ebp+var_10]
0x1002de1e  mov     ebx, [eax+34h]
0x1002de21  jmp     short loc_1002DE40
0x1002de23  lea     esi, [ebp+var_28]
0x1002de26  xor     ecx, ecx
0x1002de28  mov     edi, offset _FORMAT_VideoInfo2
0x1002de2d  mov     eax, [esi+ecx*4]
0x1002de30  cmp     eax, [edi+ecx*4]
0x1002de33  jnz     short loc_1002DE40
0x1002de35  inc     ecx
0x1002de36  cmp     ecx, edx
0x1002de38  jnz     short loc_1002DE2D
0x1002de3a  mov     eax, [ebp+var_10]
0x1002de3d  mov     ebx, [eax+4Ch]
0x1002de40  mov     ecx, [ebp+var_60]
0x1002de43  mov     ecx, [ecx+54h]
0x1002de46  test    ecx, ecx
0x1002de48  jz      loc_1002DFC9
0x1002de4e  mov     eax, [ecx]
0x1002de50  mov     esi, [eax]
0x1002de52  lea     eax, [ebp+var_5C]
0x1002de55  push    eax
0x1002de56  push    offset _IID_IDirect3DSurface9
0x1002de5b  push    ecx
0x1002de5c  mov     ecx, esi; this
0x1002de5e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002de64  call    esi
0x1002de66  mov     edi, eax
0x1002de68  mov     ecx, eax
0x1002de6a  test    edi, edi
0x1002de6c  js      loc_1002DFD0
0x1002de72  mov     esi, [ebp+var_64]
0x1002de75  lea     eax, [ebp+var_58]
0x1002de78  push    eax; unsigned int *
0x1002de79  push    [ebp+var_5C]; struct IDirect3DSurface9 *
0x1002de7c  mov     ecx, esi; this
0x1002de7e  call    ?GetSurfacePitch@CD3DSurfaceAllocator@@QAEJPAUIDirect3DSurface9@@AAK@Z; CD3DSurfaceAllocator::GetSurfacePitch(IDirect3DSurface9 *,ulong &)
0x1002de83  mov     edi, eax
0x1002de85  test    edi, edi
0x1002de87  jns     short loc_1002DEB1
0x1002de89  mov     eax, _WPP_GLOBAL_Control
0x1002de8e  cmp     eax, offset _WPP_GLOBAL_Control
0x1002de93  jz      loc_1002E017
0x1002de99  cmp     byte ptr [eax+19h], 3
0x1002de9d  jb      loc_1002E017
0x1002dea3  push    edi
0x1002dea4  push    dword ptr [eax+14h]
0x1002dea7  push    dword ptr [eax+10h]
0x1002deaa  push    2Bh ; '+'
0x1002deac  jmp     loc_1002DDC2
0x1002deb1  mov     edx, [ebp+var_58]
0x1002deb4  cmp     edx, ebx
0x1002deb6  jz      loc_1002E017
0x1002debc  lea     edi, [ebp+var_28]
0x1002debf  xor     ecx, ecx
0x1002dec1  mov     ebx, offset _FORMAT_VideoInfo
0x1002dec6  mov     eax, [edi+ecx*4]
0x1002dec9  cmp     eax, [ebx+ecx*4]
0x1002decc  jnz     short loc_1002DEDA
0x1002dece  inc     ecx
0x1002decf  cmp     ecx, 4
0x1002ded2  jnz     short loc_1002DEC6
0x1002ded4  mov     eax, [ebp+var_10]
0x1002ded7  mov     [eax+34h], edx
0x1002deda  lea     edi, [ebp+var_28]
0x1002dedd  xor     ecx, ecx
0x1002dedf  mov     ebx, offset _FORMAT_VideoInfo2
0x1002dee4  mov     eax, [edi+ecx*4]
0x1002dee7  cmp     eax, [ebx+ecx*4]
0x1002deea  jnz     short loc_1002DEF8
0x1002deec  inc     ecx
0x1002deed  cmp     ecx, 4
0x1002def0  jnz     short loc_1002DEE4
0x1002def2  mov     eax, [ebp+var_10]
0x1002def5  mov     [eax+4Ch], edx
0x1002def8  mov     ecx, [esi+80h]
0x1002defe  mov     [ebp+var_58], 0
0x1002df05  mov     eax, [ecx]
0x1002df07  mov     esi, [eax]
0x1002df09  lea     eax, [ebp+var_58]
0x1002df0c  push    eax
0x1002df0d  push    offset __GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x1002df12  push    ecx
0x1002df13  mov     ecx, esi; this
0x1002df15  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002df1b  call    esi
0x1002df1d  test    eax, eax
0x1002df1f  js      short loc_1002DF4B
0x1002df21  mov     eax, [ebp+var_58]
0x1002df24  push    eax
0x1002df25  mov     ecx, [eax]
0x1002df27  mov     esi, [ecx+14h]
0x1002df2a  mov     ecx, esi; this
0x1002df2c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002df32  call    esi
0x1002df34  mov     ecx, [ebp+var_58]
0x1002df37  mov     ebx, eax
0x1002df39  push    ecx
0x1002df3a  mov     edx, [ecx]
0x1002df3c  mov     esi, [edx+8]
0x1002df3f  mov     ecx, esi; this
0x1002df41  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002df47  call    esi
0x1002df49  jmp     short loc_1002DF4E
0x1002df4b  mov     ebx, [ebp+var_68]
0x1002df4e  mov     eax, [ebx]
0x1002df50  mov     esi, [eax+2Ch]
0x1002df53  lea     eax, [ebp+var_54]
0x1002df56  push    eax
0x1002df57  push    ebx
0x1002df58  mov     ecx, esi; this
0x1002df5a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002df60  call    esi
0x1002df62  mov     edi, eax
0x1002df64  test    edi, edi
0x1002df66  jns     short loc_1002DF90
0x1002df68  mov     eax, _WPP_GLOBAL_Control
0x1002df6d  cmp     eax, offset _WPP_GLOBAL_Control
0x1002df72  jz      loc_1002E017
0x1002df78  cmp     byte ptr [eax+19h], 3
0x1002df7c  jb      loc_1002E017
0x1002df82  push    edi
0x1002df83  push    dword ptr [eax+14h]
0x1002df86  push    dword ptr [eax+10h]
0x1002df89  push    2Ch ; ','
0x1002df8b  jmp     loc_1002DDC2
0x1002df90  mov     ecx, [ebp+var_60]
0x1002df93  mov     eax, [ecx]
0x1002df95  mov     esi, [eax+38h]
0x1002df98  lea     eax, [ebp+var_54]
0x1002df9b  push    eax
0x1002df9c  push    ecx
0x1002df9d  mov     ecx, esi; this
0x1002df9f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002dfa5  call    esi
0x1002dfa7  mov     edi, eax
0x1002dfa9  mov     eax, _WPP_GLOBAL_Control
0x1002dfae  cmp     eax, offset _WPP_GLOBAL_Control
0x1002dfb3  jz      short loc_1002E017
0x1002dfb5  cmp     byte ptr [eax+19h], 3
0x1002dfb9  jb      short loc_1002E017
0x1002dfbb  push    edi
0x1002dfbc  push    dword ptr [eax+14h]
0x1002dfbf  push    dword ptr [eax+10h]
0x1002dfc2  push    2Dh ; '-'
0x1002dfc4  jmp     loc_1002DDC2
0x1002dfc9  mov     edi, 8000FFFFh
0x1002dfce  mov     ecx, edi
0x1002dfd0  mov     eax, _WPP_GLOBAL_Control
0x1002dfd5  cmp     eax, offset _WPP_GLOBAL_Control
0x1002dfda  jz      short loc_1002E017
0x1002dfdc  cmp     byte ptr [eax+19h], 3
0x1002dfe0  jb      short loc_1002E017
0x1002dfe2  push    ecx
0x1002dfe3  push    dword ptr [eax+14h]
0x1002dfe6  push    dword ptr [eax+10h]
0x1002dfe9  push    2Ah ; '*'
0x1002dfeb  jmp     loc_1002DDC2
0x1002dff0  xor     edi, edi
0x1002dff2  mov     eax, _WPP_GLOBAL_Control
0x1002dff7  cmp     eax, offset _WPP_GLOBAL_Control
0x1002dffc  jz      short loc_1002E017
0x1002dffe  cmp     byte ptr [eax+19h], 3
0x1002e002  jb      short loc_1002E017
0x1002e004  push    dword ptr [eax+14h]
0x1002e007  push    dword ptr [eax+10h]; LoggerHandle
0x1002e00a  push    29h ; ')'
0x1002e00c  mov     edx, offset _WPP_456c1cc922103473f2b3500a0e641fc7_Traceguids; MessageGuid
0x1002e011  pop     ecx; MessageNumber
0x1002e012  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1002e017  lea     ecx, [ebp+var_54]
0x1002e01a  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1002e01f  mov     ecx, [ebp+var_5C]
0x1002e022  test    ecx, ecx
0x1002e024  jz      short loc_1002E036
0x1002e026  mov     eax, [ecx]
0x1002e028  push    ecx
0x1002e029  mov     esi, [eax+8]
0x1002e02c  mov     ecx, esi; this
0x1002e02e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002e034  call    esi
0x1002e036  mov     ecx, [ebp+var_8]
0x1002e039  mov     eax, edi
0x1002e03b  pop     edi
0x1002e03c  pop     esi
0x1002e03d  xor     ecx, ebp; StackCookie
0x1002e03f  pop     ebx
0x1002e040  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002e045  leave
0x1002e046  retn    4
```
