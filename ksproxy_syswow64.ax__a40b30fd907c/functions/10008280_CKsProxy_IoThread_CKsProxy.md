# CKsProxy::IoThread(CKsProxy *)

- ea: `0x10008280`
- end: `0x10008423`
- name: `?IoThread@CKsProxy@@SGKPAV1@@Z`
- size: `419`
- prototype: `ULONG __stdcall(char *Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x100063f1`
- `0x10006415`
- `0x10008280`
- `0x1002d510`
- `0x1003bd04`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1000833e`
- `KERNEL32!CloseHandle` at `0x1000833e`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x100082cf`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x100082cf`
- `KERNEL32!LeaveCriticalSection` at `0x100083b3`
- `KERNEL32!LeaveCriticalSection` at `0x100083df`
- `KERNEL32!LeaveCriticalSection` at `0x100083ea`
- `KERNEL32!LeaveCriticalSection` at `0x100083b3`
- `KERNEL32!LeaveCriticalSection` at `0x100083df`
- `KERNEL32!LeaveCriticalSection` at `0x100083ea`
- `KERNEL32!ReleaseSemaphore` at `0x100083c3`
- `KERNEL32!ReleaseSemaphore` at `0x100083c3`
- `KERNEL32!EnterCriticalSection` at `0x10008358`
- `KERNEL32!EnterCriticalSection` at `0x100083cf`
- `KERNEL32!EnterCriticalSection` at `0x10008358`
- `KERNEL32!EnterCriticalSection` at `0x100083cf`

## pseudocode

```c
ULONG __stdcall CKsProxy::IoThread(char *Parameter)
{
  struct _RTL_CRITICAL_SECTION *i; // esi
  DWORD v2; // eax
  DWORD v3; // ebx
  int v4; // eax
  int v5; // edx
  _DWORD *v7; // [esp-4h] [ebp-14h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      0xAu,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((const unsigned __int16 **)Parameter + 15));
  for ( i = (struct _RTL_CRITICAL_SECTION *)(Parameter + 244); ; LeaveCriticalSection(i) )
  {
    while ( 1 )
    {
      v2 = WaitForMultipleObjectsEx(*((_DWORD *)Parameter + 70), *((const HANDLE **)Parameter + 68), 0, 0xFFFFFFFF, 0);
      v3 = v2;
      if ( !v2 )
        break;
      if ( v2 != -1 )
      {
        if ( v2 <= 0x3F )
        {
          _mm_lfence();
          v7 = *(_DWORD **)(*((_DWORD *)Parameter + 69) + 4 * v2);
          (*(void (__thiscall **)(_DWORD, _DWORD, _DWORD *))(*(_DWORD *)*v7 + 20))(
            *(_DWORD *)(*(_DWORD *)*v7 + 20),
            *v7,
            v7);
          v4 = *((_DWORD *)Parameter + 68);
          if ( *(_DWORD *)(v4 + 4 * v3) )
          {
            CloseHandle(*(HANDLE *)(v4 + 4 * v3));
            *(_DWORD *)(*((_DWORD *)Parameter + 68) + 4 * v3) = 0;
          }
          i = (struct _RTL_CRITICAL_SECTION *)(Parameter + 244);
          EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 244));
          v5 = *((_DWORD *)Parameter + 70) - 1;
          *((_DWORD *)Parameter + 70) = v5;
          if ( v5 > 1 && v3 != v5 )
          {
            memmove(
              (void *)(*((_DWORD *)Parameter + 68) + 4 * v3),
              (const void *)(*((_DWORD *)Parameter + 68) + 4 * v3 + 4),
              4 * (v5 - v3));
            memmove(
              (void *)(*((_DWORD *)Parameter + 69) + 4 * v3),
              (const void *)(*((_DWORD *)Parameter + 69) + 4 * v3 + 4),
              4 * (*((_DWORD *)Parameter + 70) - v3));
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 244));
          ReleaseSemaphore(*((HANDLE *)Parameter + 67), 1, 0);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(0xCu, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
        }
      }
    }
    EnterCriticalSection(i);
    if ( *((_DWORD *)Parameter + 60) )
      break;
  }
  LeaveCriticalSection(i);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_S(
      0xBu,
      &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids,
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((const unsigned __int16 **)Parameter + 15));
  return 0;
}

```

## disassembly

```asm
0x10008280  mov     edi, edi
0x10008282  push    ebp
0x10008283  mov     ebp, esp
0x10008285  and     esp, 0FFFFFFF8h
0x10008288  push    ecx
0x10008289  push    ebx
0x1000828a  push    esi
0x1000828b  push    edi
0x1000828c  mov     edi, [ebp+Parameter]
0x1000828f  mov     eax, _WPP_GLOBAL_Control
0x10008294  cmp     eax, offset _WPP_GLOBAL_Control
0x10008299  jz      short loc_100082B7
0x1000829b  cmp     byte ptr [eax+19h], 2
0x1000829f  jb      short loc_100082B7
0x100082a1  push    dword ptr [edi+3Ch]; int
0x100082a4  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x100082a9  push    dword ptr [eax+14h]
0x100082ac  push    dword ptr [eax+10h]; LoggerHandle
0x100082af  push    0Ah
0x100082b1  pop     ecx; MessageNumber
0x100082b2  call    _WPP_SF_S@20; WPP_SF_S(x,x,x,x,x)
0x100082b7  lea     esi, [edi+0F4h]
0x100082bd  push    0; bAlertable
0x100082bf  push    0FFFFFFFFh; dwMilliseconds
0x100082c1  push    0; bWaitAll
0x100082c3  push    dword ptr [edi+110h]; lpHandles
0x100082c9  push    dword ptr [edi+118h]; nCount
0x100082cf  call    ds:__imp__WaitForMultipleObjectsEx@20; WaitForMultipleObjectsEx(x,x,x,x,x)
0x100082d5  mov     ebx, eax
0x100082d7  test    ebx, ebx
0x100082d9  jz      loc_100083CE
0x100082df  cmp     ebx, 0FFFFFFFFh
0x100082e2  jz      short loc_100082BD
0x100082e4  cmp     ebx, 3Fh ; '?'
0x100082e7  jbe     short loc_10008310
0x100082e9  mov     eax, _WPP_GLOBAL_Control
0x100082ee  cmp     eax, offset _WPP_GLOBAL_Control
0x100082f3  jz      short loc_100082BD
0x100082f5  cmp     byte ptr [eax+19h], 2
0x100082f9  jb      short loc_100082BD
0x100082fb  push    dword ptr [eax+14h]
0x100082fe  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x10008303  push    dword ptr [eax+10h]; LoggerHandle
0x10008306  push    0Ch
0x10008308  pop     ecx; MessageNumber
0x10008309  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1000830e  jmp     short loc_100082BD
0x10008310  lfence
0x10008313  mov     eax, [edi+114h]
0x10008319  mov     eax, [eax+ebx*4]
0x1000831c  push    eax
0x1000831d  mov     ecx, [eax]
0x1000831f  push    ecx
0x10008320  mov     edx, [ecx]
0x10008322  mov     esi, [edx+14h]
0x10008325  mov     ecx, esi; this
0x10008327  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1000832d  call    esi
0x1000832f  mov     eax, [edi+110h]
0x10008335  cmp     dword ptr [eax+ebx*4], 0
0x10008339  jz      short loc_10008351
0x1000833b  push    dword ptr [eax+ebx*4]; hObject
0x1000833e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10008344  mov     eax, [edi+110h]
0x1000834a  mov     dword ptr [eax+ebx*4], 0
0x10008351  lea     esi, [edi+0F4h]
0x10008357  push    esi; lpCriticalSection
0x10008358  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000835e  mov     edx, [edi+118h]
0x10008364  dec     edx
0x10008365  mov     [edi+118h], edx
0x1000836b  cmp     edx, 1
0x1000836e  jle     short loc_100083B2
0x10008370  cmp     ebx, edx
0x10008372  jz      short loc_100083B2
0x10008374  mov     eax, [edi+110h]
0x1000837a  sub     edx, ebx
0x1000837c  shl     edx, 2
0x1000837f  push    edx; Size
0x10008380  lea     ecx, [eax+ebx*4]
0x10008383  lea     eax, [ecx+4]
0x10008386  push    eax; Src
0x10008387  push    ecx; void *
0x10008388  call    _memmove
0x1000838d  mov     eax, [edi+114h]
0x10008393  add     esp, 0Ch
0x10008396  lea     ecx, [eax+ebx*4]
0x10008399  mov     eax, [edi+118h]
0x1000839f  sub     eax, ebx
0x100083a1  shl     eax, 2
0x100083a4  push    eax; Size
0x100083a5  lea     eax, [ecx+4]
0x100083a8  push    eax; Src
0x100083a9  push    ecx; void *
0x100083aa  call    _memmove
0x100083af  add     esp, 0Ch
0x100083b2  push    esi; lpCriticalSection
0x100083b3  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100083b9  push    0; lpPreviousCount
0x100083bb  push    1; lReleaseCount
0x100083bd  push    dword ptr [edi+10Ch]; hSemaphore
0x100083c3  call    ds:__imp__ReleaseSemaphore@12; ReleaseSemaphore(x,x,x)
0x100083c9  jmp     loc_100082BD
0x100083ce  push    esi; lpCriticalSection
0x100083cf  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100083d5  cmp     dword ptr [edi+0F0h], 0
0x100083dc  push    esi; lpCriticalSection
0x100083dd  jnz     short loc_100083EA
0x100083df  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100083e5  jmp     loc_100082BD
0x100083ea  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100083f0  mov     eax, _WPP_GLOBAL_Control
0x100083f5  cmp     eax, offset _WPP_GLOBAL_Control
0x100083fa  jz      short loc_10008418
0x100083fc  cmp     byte ptr [eax+19h], 2
0x10008400  jb      short loc_10008418
0x10008402  push    dword ptr [edi+3Ch]; int
0x10008405  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x1000840a  push    dword ptr [eax+14h]
0x1000840d  push    dword ptr [eax+10h]; LoggerHandle
0x10008410  push    0Bh
0x10008412  pop     ecx; MessageNumber
0x10008413  call    _WPP_SF_S@20; WPP_SF_S(x,x,x,x,x)
0x10008418  pop     edi
0x10008419  pop     esi
0x1000841a  xor     eax, eax
0x1000841c  pop     ebx
0x1000841d  mov     esp, ebp
0x1000841f  pop     ebp
0x10008420  retn    4
```
