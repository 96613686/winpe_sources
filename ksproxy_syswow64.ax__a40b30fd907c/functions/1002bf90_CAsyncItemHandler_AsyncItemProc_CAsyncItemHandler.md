# CAsyncItemHandler::AsyncItemProc(CAsyncItemHandler *)

- ea: `0x1002bf90`
- end: `0x1002c2ff`
- name: `?AsyncItemProc@CAsyncItemHandler@@KGKPAV1@@Z`
- size: `879`
- prototype: `ULONG __stdcall(char *Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1000665f`
- `0x10006689`
- `0x1001f043`
- `0x1002bf90`
- `0x1002c343`
- `0x1002d510`
- `0x1003bd04`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1002c247`
- `KERNEL32!GetLastError` at `0x1002c247`
- `KERNEL32!SetEvent` at `0x1002c14f`
- `KERNEL32!SetEvent` at `0x1002c14f`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002c045`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002c188`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002c045`
- `KERNEL32!WaitForSingleObjectEx` at `0x1002c188`
- `KERNEL32!ReleaseMutex` at `0x1002c130`
- `KERNEL32!ReleaseMutex` at `0x1002c21b`
- `KERNEL32!ReleaseMutex` at `0x1002c130`
- `KERNEL32!ReleaseMutex` at `0x1002c21b`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1002bfb7`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1002bfb7`
- `KERNEL32!ReleaseSemaphore` at `0x1002c143`
- `KERNEL32!ReleaseSemaphore` at `0x1002c22e`
- `KERNEL32!ReleaseSemaphore` at `0x1002c143`
- `KERNEL32!ReleaseSemaphore` at `0x1002c22e`
- `KERNEL32!GetHandleInformation` at `0x1002bfcf`
- `KERNEL32!GetHandleInformation` at `0x1002bfcf`

## pseudocode

```c
ULONG __stdcall CAsyncItemHandler::AsyncItemProc(char *Parameter)
{
  DWORD v1; // esi
  DWORD v2; // eax
  char v3; // bl
  int v4; // eax
  int v5; // eax
  unsigned int v6; // ecx
  LONG v7; // esi
  unsigned int v8; // ebx
  int *v9; // eax
  int v10; // esi
  char v11; // bl
  unsigned int v12; // eax
  int *v13; // ecx
  int v14; // esi
  LONG v15; // esi
  char LastError; // al
  unsigned int v17; // eax
  unsigned int v18; // ebx
  int v19; // esi
  int v20; // ecx
  int v22; // [esp-4h] [ebp-1Ch]
  struct _ITEM_LIST_HEAD *v23; // [esp+0h] [ebp-18h]
  struct _ITEM_LIST_ITEM *v24; // [esp+4h] [ebp-14h]
  DWORD v25; // [esp+10h] [ebp-8h]
  LONG i; // [esp+10h] [ebp-8h]
  unsigned int j; // [esp+10h] [ebp-8h]
  DWORD dwFlags; // [esp+14h] [ebp-4h] BYREF

  do
  {
    v1 = 64;
    if ( *((_DWORD *)Parameter + 128) < 0x40u )
      v1 = *((_DWORD *)Parameter + 128);
    v2 = WaitForMultipleObjectsEx(v1, (const HANDLE *)Parameter, 0, 0xFFFFFFFF, 0);
    v3 = v2;
    v25 = v2;
    if ( v2 == -1 )
    {
      if ( !GetHandleInformation(*(HANDLE *)Parameter, &dwFlags) )
        break;
    }
    else
    {
      if ( v2 >= v1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          WPP_SF_qq(
            0xD0u,
            &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v3,
            LastError);
        }
        continue;
      }
      if ( v2 )
      {
        v22 = *(_DWORD *)&Parameter[4 * v2 + 256];
        v11 = *(_BYTE *)(v22 + 8);
        (*(void (__thiscall **)(_DWORD, _DWORD, int))(v22 + 16))(*(_DWORD *)(v22 + 16), 0, v22);
        if ( !v11 )
          goto LABEL_31;
        WaitForSingleObjectEx(*((HANDLE *)Parameter + 140), 0xFFFFFFFF, 0);
        v12 = *((_DWORD *)Parameter + 128) - 1;
        *((_DWORD *)Parameter + 128) = v12;
        if ( v25 < v12 )
        {
          memmove(&Parameter[4 * v25], &Parameter[4 * v25 + 4], 4 * (v12 - v25));
          memmove(&Parameter[4 * v25 + 256], &Parameter[4 * v25 + 260], 4 * (*((_DWORD *)Parameter + 128) - v25));
        }
        v13 = (int *)(Parameter + 528);
        if ( *((_DWORD *)Parameter + 136) && (v14 = *v13) != 0 )
        {
          ItemListRemoveItem(v23, v24);
          *(_DWORD *)&Parameter[4 * *((_DWORD *)Parameter + 128)] = *(_DWORD *)(v14 + 12);
          *(_DWORD *)&Parameter[4 * (*((_DWORD *)Parameter + 128))++ + 256] = v14;
LABEL_31:
          v15 = 0;
        }
        else
        {
          v15 = 1;
        }
        ReleaseMutex(*((HANDLE *)Parameter + 140));
        if ( v15 )
          ReleaseSemaphore(*((HANDLE *)Parameter + 139), v15, 0);
        continue;
      }
      v4 = *((_DWORD *)Parameter + 129);
      if ( !v4 )
        goto LABEL_24;
      v5 = v4 - 1;
      if ( !v5 )
        goto LABEL_24;
      if ( v5 == 1 )
      {
        WaitForSingleObjectEx(*((HANDLE *)Parameter + 140), 0xFFFFFFFF, 0);
        v6 = *((_DWORD *)Parameter + 128);
        v7 = 0;
        v8 = 1;
        for ( i = 0; v8 < v6; ++v8 )
        {
          if ( *(_DWORD *)&Parameter[4 * v8] == *((_DWORD *)Parameter + 130) )
          {
            (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)&Parameter[4 * v8 + 256] + 16))(
              *(_DWORD *)(*(_DWORD *)&Parameter[4 * v8 + 256] + 16),
              1,
              *(_DWORD *)&Parameter[4 * v8 + 256]);
            v6 = *((_DWORD *)Parameter + 128) - 1;
            *((_DWORD *)Parameter + 128) = v6;
            if ( v8 < v6 )
            {
              memmove(Parameter, Parameter + 4, 4 * v6);
              memmove(Parameter + 256, Parameter + 260, 4 * *((_DWORD *)Parameter + 128));
              v6 = *((_DWORD *)Parameter + 128);
            }
            v9 = (int *)(Parameter + 528);
            if ( *((_DWORD *)Parameter + 136) && (v10 = *v9) != 0 )
            {
              ItemListRemoveItem(v23, v24);
              *(_DWORD *)&Parameter[4 * *((_DWORD *)Parameter + 128)] = *(_DWORD *)(v10 + 12);
              *(_DWORD *)&Parameter[4 * (*((_DWORD *)Parameter + 128))++ + 256] = v10;
              v6 = *((_DWORD *)Parameter + 128);
              v7 = i;
            }
            else
            {
              v7 = ++i;
            }
          }
        }
        ReleaseMutex(*((HANDLE *)Parameter + 140));
        if ( v7 )
          ReleaseSemaphore(*((HANDLE *)Parameter + 139), v7, 0);
LABEL_24:
        SetEvent(*((HANDLE *)Parameter + 131));
        continue;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_q(
          0xD1u,
          &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_DWORD *)Parameter + 129));
    }
  }
  while ( *((_DWORD *)Parameter + 129) );
  v17 = *((_DWORD *)Parameter + 128);
  v18 = 1;
  for ( j = v17; v18 < v17; ++v18 )
  {
    v19 = *(_DWORD *)&Parameter[4 * v18 + 256];
    if ( v19 && !*(_BYTE *)(v19 + 8) )
    {
      (*(void (__thiscall **)(_DWORD, int, _DWORD))(v19 + 16))(
        *(_DWORD *)(v19 + 16),
        1,
        *(_DWORD *)&Parameter[4 * v18 + 256]);
      --*((_DWORD *)Parameter + 128);
      v17 = j;
    }
  }
  v20 = *((_DWORD *)Parameter + 128) - 1;
  *((_DWORD *)Parameter + 128) = v20;
  if ( (v20 || *((_DWORD *)Parameter + 136)) && WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 2), (char)Parameter, v20, *((_DWORD *)Parameter + 136));
  return *((_DWORD *)Parameter + 128);
}

```

## disassembly

```asm
0x1002bf90  mov     edi, edi
0x1002bf92  push    ebp
0x1002bf93  mov     ebp, esp
0x1002bf95  and     esp, 0FFFFFFF8h
0x1002bf98  sub     esp, 0Ch
0x1002bf9b  push    ebx
0x1002bf9c  push    esi; struct _ITEM_LIST_ITEM *
0x1002bf9d  push    edi; struct _ITEM_LIST_HEAD *
0x1002bf9e  mov     edi, [ebp+Parameter]
0x1002bfa1  mov     eax, [edi+200h]
0x1002bfa7  push    40h ; '@'
0x1002bfa9  pop     esi
0x1002bfaa  push    0; bAlertable
0x1002bfac  push    0FFFFFFFFh; dwMilliseconds
0x1002bfae  cmp     eax, esi
0x1002bfb0  push    0; bWaitAll
0x1002bfb2  cmovb   esi, eax
0x1002bfb5  push    edi; lpHandles
0x1002bfb6  push    esi; nCount
0x1002bfb7  call    ds:__imp__WaitForMultipleObjectsEx@20; WaitForMultipleObjectsEx(x,x,x,x,x)
0x1002bfbd  mov     ebx, eax
0x1002bfbf  mov     [esp+18h+var_8], ebx
0x1002bfc3  cmp     ebx, 0FFFFFFFFh
0x1002bfc6  jnz     short loc_1002BFE2
0x1002bfc8  lea     eax, [esp+18h+dwFlags]
0x1002bfcc  push    eax; lpdwFlags
0x1002bfcd  push    dword ptr [edi]; hObject
0x1002bfcf  call    ds:__imp__GetHandleInformation@8; GetHandleInformation(x,x)
0x1002bfd5  test    eax, eax
0x1002bfd7  jz      loc_1002C276
0x1002bfdd  jmp     loc_1002C269
0x1002bfe2  cmp     ebx, esi
0x1002bfe4  jnb     loc_1002C23B
0x1002bfea  test    ebx, ebx
0x1002bfec  jnz     loc_1002C15A
0x1002bff2  mov     ecx, [edi+204h]
0x1002bff8  mov     eax, ecx
0x1002bffa  sub     eax, ebx
0x1002bffc  jz      loc_1002C149
0x1002c002  sub     eax, 1
0x1002c005  jz      loc_1002C149
0x1002c00b  sub     eax, 1
0x1002c00e  jz      short loc_1002C03B
0x1002c010  mov     eax, _WPP_GLOBAL_Control
0x1002c015  cmp     eax, offset _WPP_GLOBAL_Control
0x1002c01a  jz      loc_1002C269
0x1002c020  push    ecx; char
0x1002c021  push    dword ptr [eax+14h]
0x1002c024  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002c029  mov     ecx, 0D1h; MessageNumber
0x1002c02e  push    dword ptr [eax+10h]; LoggerHandle
0x1002c031  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x1002c036  jmp     loc_1002C269
0x1002c03b  push    0; bAlertable
0x1002c03d  push    0FFFFFFFFh; dwMilliseconds
0x1002c03f  push    dword ptr [edi+230h]; hHandle
0x1002c045  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1002c04b  mov     ecx, [edi+200h]
0x1002c051  xor     ebx, ebx
0x1002c053  xor     esi, esi
0x1002c055  inc     ebx
0x1002c056  mov     [esp+18h+var_8], esi
0x1002c05a  cmp     ecx, ebx
0x1002c05c  jbe     loc_1002C12A
0x1002c062  mov     eax, [edi+ebx*4]
0x1002c065  cmp     eax, [edi+208h]
0x1002c06b  jnz     loc_1002C121
0x1002c071  mov     eax, [edi+ebx*4+100h]
0x1002c078  push    eax
0x1002c079  push    1
0x1002c07b  mov     esi, [eax+10h]
0x1002c07e  mov     ecx, esi; this
0x1002c080  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c086  call    esi
0x1002c088  mov     ecx, [edi+200h]
0x1002c08e  dec     ecx
0x1002c08f  mov     [edi+200h], ecx
0x1002c095  cmp     ebx, ecx
0x1002c097  jnb     short loc_1002C0D2
0x1002c099  mov     eax, ecx
0x1002c09b  shl     eax, 2
0x1002c09e  push    eax; Size
0x1002c09f  lea     eax, [edi+4]
0x1002c0a2  push    eax; Src
0x1002c0a3  push    edi; void *
0x1002c0a4  call    _memmove
0x1002c0a9  mov     eax, [edi+200h]
0x1002c0af  add     esp, 0Ch
0x1002c0b2  shl     eax, 2
0x1002c0b5  push    eax; Size
0x1002c0b6  lea     eax, [edi+104h]
0x1002c0bc  push    eax; Src
0x1002c0bd  lea     eax, [edi+100h]
0x1002c0c3  push    eax; void *
0x1002c0c4  call    _memmove
0x1002c0c9  mov     ecx, [edi+200h]
0x1002c0cf  add     esp, 0Ch
0x1002c0d2  lea     eax, [edi+210h]
0x1002c0d8  cmp     dword ptr [eax+10h], 0
0x1002c0dc  jbe     short loc_1002C118
0x1002c0de  mov     esi, [eax]
0x1002c0e0  test    esi, esi
0x1002c0e2  jz      short loc_1002C118
0x1002c0e4  mov     edx, esi
0x1002c0e6  mov     ecx, eax
0x1002c0e8  call    ?ItemListRemoveItem@@YGPAU_ITEM_LIST_ITEM@@PAU_ITEM_LIST_HEAD@@PAU1@@Z; ItemListRemoveItem(_ITEM_LIST_HEAD *,_ITEM_LIST_ITEM *)
0x1002c0ed  mov     ecx, [edi+200h]
0x1002c0f3  mov     eax, [esi+0Ch]
0x1002c0f6  mov     [edi+ecx*4], eax
0x1002c0f9  mov     eax, [edi+200h]
0x1002c0ff  mov     [edi+eax*4+100h], esi
0x1002c106  inc     dword ptr [edi+200h]
0x1002c10c  mov     ecx, [edi+200h]
0x1002c112  mov     esi, [esp+18h+var_8]
0x1002c116  jmp     short loc_1002C121
0x1002c118  mov     esi, [esp+18h+var_8]
0x1002c11c  inc     esi
0x1002c11d  mov     [esp+18h+var_8], esi
0x1002c121  inc     ebx
0x1002c122  cmp     ebx, ecx
0x1002c124  jb      loc_1002C062
0x1002c12a  push    dword ptr [edi+230h]; hMutex
0x1002c130  call    ds:__imp__ReleaseMutex@4; ReleaseMutex(x)
0x1002c136  test    esi, esi
0x1002c138  jz      short loc_1002C149
0x1002c13a  push    0; lpPreviousCount
0x1002c13c  push    esi; lReleaseCount
0x1002c13d  push    dword ptr [edi+22Ch]; hSemaphore
0x1002c143  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x1002c149  push    dword ptr [edi+20Ch]; hEvent
0x1002c14f  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1002c155  jmp     loc_1002C269
0x1002c15a  lea     eax, [edi+ebx*4]
0x1002c15d  mov     eax, [eax+100h]
0x1002c163  push    eax
0x1002c164  push    0
0x1002c166  mov     esi, [eax+10h]
0x1002c169  mov     ecx, esi; this
0x1002c16b  mov     bl, [eax+8]
0x1002c16e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c174  call    esi
0x1002c176  test    bl, bl
0x1002c178  jz      loc_1002C213
0x1002c17e  push    0; bAlertable
0x1002c180  push    0FFFFFFFFh; dwMilliseconds
0x1002c182  push    dword ptr [edi+230h]; hHandle
0x1002c188  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1002c18e  mov     eax, [edi+200h]
0x1002c194  mov     esi, [esp+18h+var_8]
0x1002c198  dec     eax
0x1002c199  mov     [edi+200h], eax
0x1002c19f  cmp     esi, eax
0x1002c1a1  jnb     short loc_1002C1DB
0x1002c1a3  sub     eax, esi
0x1002c1a5  lea     ecx, [edi+esi*4]
0x1002c1a8  shl     eax, 2
0x1002c1ab  push    eax; Size
0x1002c1ac  lea     eax, [ecx+4]
0x1002c1af  push    eax; Src
0x1002c1b0  push    ecx; void *
0x1002c1b1  call    _memmove
0x1002c1b6  mov     eax, [edi+200h]
0x1002c1bc  add     esp, 0Ch
0x1002c1bf  sub     eax, esi
0x1002c1c1  shl     eax, 2
0x1002c1c4  push    eax; Size
0x1002c1c5  lea     eax, [esi+41h]
0x1002c1c8  lea     eax, [edi+eax*4]
0x1002c1cb  push    eax; Src
0x1002c1cc  lea     eax, [esi+40h]
0x1002c1cf  lea     eax, [edi+eax*4]
0x1002c1d2  push    eax; void *
0x1002c1d3  call    _memmove
0x1002c1d8  add     esp, 0Ch
0x1002c1db  lea     ecx, [edi+210h]
0x1002c1e1  cmp     dword ptr [ecx+10h], 0
0x1002c1e5  jbe     short loc_1002C236
0x1002c1e7  mov     esi, [ecx]
0x1002c1e9  test    esi, esi
0x1002c1eb  jz      short loc_1002C236
0x1002c1ed  mov     edx, esi
0x1002c1ef  call    ?ItemListRemoveItem@@YGPAU_ITEM_LIST_ITEM@@PAU_ITEM_LIST_HEAD@@PAU1@@Z; ItemListRemoveItem(_ITEM_LIST_HEAD *,_ITEM_LIST_ITEM *)
0x1002c1f4  mov     ecx, [edi+200h]
0x1002c1fa  mov     eax, [esi+0Ch]
0x1002c1fd  mov     [edi+ecx*4], eax
0x1002c200  mov     eax, [edi+200h]
0x1002c206  mov     [edi+eax*4+100h], esi
0x1002c20d  inc     dword ptr [edi+200h]
0x1002c213  xor     esi, esi
0x1002c215  push    dword ptr [edi+230h]; hMutex
0x1002c21b  call    ds:__imp__ReleaseMutex@4; ReleaseMutex(x)
0x1002c221  test    esi, esi
0x1002c223  jz      short loc_1002C269
0x1002c225  push    0; lpPreviousCount
0x1002c227  push    esi; lReleaseCount
0x1002c228  push    dword ptr [edi+22Ch]; hSemaphore
0x1002c22e  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x1002c234  jmp     short loc_1002C269
0x1002c236  xor     esi, esi
0x1002c238  inc     esi
0x1002c239  jmp     short loc_1002C215
0x1002c23b  cmp     _WPP_GLOBAL_Control, offset _WPP_GLOBAL_Control
0x1002c245  jz      short loc_1002C269
0x1002c247  call    ds:__imp__GetLastError@0; GetLastError()
0x1002c24d  push    eax; char
0x1002c24e  mov     eax, _WPP_GLOBAL_Control
0x1002c253  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1002c258  push    ebx; char
0x1002c259  mov     ecx, 0D0h; MessageNumber
0x1002c25e  push    dword ptr [eax+14h]
0x1002c261  push    dword ptr [eax+10h]; LoggerHandle
0x1002c264  call    _WPP_SF_qq@24; WPP_SF_qq(x,x,x,x,x,x)
0x1002c269  cmp     dword ptr [edi+204h], 0
0x1002c270  jnz     loc_1002BFA1
0x1002c276  mov     eax, [edi+200h]
0x1002c27c  xor     ebx, ebx
0x1002c27e  inc     ebx
0x1002c27f  mov     [esp+18h+var_8], eax
0x1002c283  cmp     eax, ebx
0x1002c285  jbe     short loc_1002C2B7
0x1002c287  mov     esi, [edi+ebx*4+100h]
0x1002c28e  test    esi, esi
0x1002c290  jz      short loc_1002C2B2
0x1002c292  cmp     byte ptr [esi+8], 0
0x1002c296  jnz     short loc_1002C2B2
0x1002c298  push    esi
0x1002c299  mov     esi, [esi+10h]
0x1002c29c  mov     ecx, esi; this
0x1002c29e  push    1
0x1002c2a0  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1002c2a6  call    esi
0x1002c2a8  dec     dword ptr [edi+200h]
0x1002c2ae  mov     eax, [esp+18h+var_8]
0x1002c2b2  inc     ebx
0x1002c2b3  cmp     ebx, eax
0x1002c2b5  jb      short loc_1002C287
0x1002c2b7  mov     ecx, [edi+200h]
0x1002c2bd  sub     ecx, 1
0x1002c2c0  mov     [edi+200h], ecx
0x1002c2c6  jnz     short loc_1002C2D1
0x1002c2c8  cmp     dword ptr [edi+220h], 0
0x1002c2cf  jbe     short loc_1002C2F0
0x1002c2d1  mov     eax, _WPP_GLOBAL_Control
0x1002c2d6  cmp     eax, offset _WPP_GLOBAL_Control
0x1002c2db  jz      short loc_1002C2F0
0x1002c2dd  push    dword ptr [edi+220h]; char
0x1002c2e3  push    ecx; char
0x1002c2e4  push    edi; char
0x1002c2e5  push    dword ptr [eax+14h]
0x1002c2e8  push    dword ptr [eax+10h]; LoggerHandle
0x1002c2eb  call    _WPP_SF_qdd@28; WPP_SF_qdd(x,x,x,x,x,x,x)
0x1002c2f0  mov     eax, [edi+200h]
0x1002c2f6  pop     edi
0x1002c2f7  pop     esi
0x1002c2f8  pop     ebx
0x1002c2f9  mov     esp, ebp
0x1002c2fb  pop     ebp
0x1002c2fc  retn    4
```
