# CImpIRowsetUpdate::GetPendingRows(ulong,ulong,ulong *,ulong * *,ulong * *)

- ea: `0x10033170`
- end: `0x100334e3`
- name: `?GetPendingRows@CImpIRowsetUpdate@@UAGJKKPAKPAPAK1@Z`
- size: `883`
- prototype: `int(CImpIRowsetUpdate *__hidden this, unsigned int, unsigned int, unsigned int *, unsigned int **, unsigned int **)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x1000ba90`
- `0x1000bb80`
- `0x1001c380`
- `0x1001c6d0`
- `0x10033170`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100334c7`
- `KERNEL32!LeaveCriticalSection` at `0x100334c7`
- `KERNEL32!EnterCriticalSection` at `0x10033222`
- `KERNEL32!EnterCriticalSection` at `0x10033222`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100331a4`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100331a4`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003339f`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003339f`

## pseudocode

```c
int __stdcall CImpIRowsetUpdate::GetPendingRows(
        struct _RTL_CRITICAL_SECTION **this,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int **a5,
        unsigned int **a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // esi
  CImpIRowsetUpdate *v7; // ebx
  struct _RTL_CRITICAL_SECTION *v8; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v10; // ecx
  int isZombie; // eax
  struct _RTL_CRITICAL_SECTION *v12; // ecx
  unsigned int v13; // edi
  int v14; // esi
  _DWORD *v15; // ebx
  int v16; // ecx
  int v17; // eax
  int v18; // ebx
  struct _GUID *v20; // [esp+0h] [ebp-30h]
  unsigned int *v21; // [esp+0h] [ebp-30h]
  unsigned int v22; // [esp+4h] [ebp-2Ch]
  unsigned int v23; // [esp+4h] [ebp-2Ch]
  int v24; // [esp+10h] [ebp-20h] BYREF
  int v25; // [esp+14h] [ebp-1Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [esp+18h] [ebp-18h]
  int v27; // [esp+20h] [ebp-10h]
  int v28; // [esp+2Ch] [ebp-4h]

  v25 = 0;
  v24 = 0;
  SetErrorInfo(0, 0);
  v6 = 0;
  lpCriticalSection = 0;
  v28 = 0;
  if ( a4 )
  {
    *a4 = 0;
    if ( a5 )
      *a5 = 0;
    if ( a6 )
      *a6 = 0;
  }
  v7 = (CImpIRowsetUpdate *)this;
  v8 = this[2];
  LockSemaphore = v8[2].LockSemaphore;
  if ( LockSemaphore )
  {
    if ( LockSemaphore[4] == 1 && (v10 = (CTransactionState *)LockSemaphore[2]) != 0 )
      isZombie = CTransactionState::isZombie(v10);
    else
      isZombie = LockSemaphore[3];
    if ( isZombie == 1 )
    {
      v27 = -2147418113;
LABEL_31:
      v18 = v27;
      if ( !JetGetDatabaseInfo(
              *(_DWORD *)(this[2][2].RecursionCount + 16),
              *(_DWORD *)(this[2][2].RecursionCount + 20),
              &v24,
              4,
              3) )
        CExtError::SendHRtoOLEAuto(v18, (__int128 *)&IID_IRowsetUpdate, 0, v20, v22);
      if ( v25 )
      {
        if ( Sys )
          (*(void (__thiscall **)(_DWORD, int, _DWORD))(*(_DWORD *)Sys + 20))(
            *(_DWORD *)(*(_DWORD *)Sys + 20),
            Sys,
            *a5);
        *a5 = 0;
      }
      goto LABEL_38;
    }
  }
  if ( ((int)v8[4].DebugInfo & 0x400) != 0 )
  {
    v27 = -2147217888;
    goto LABEL_31;
  }
  v6 = v8 + 3;
  lpCriticalSection = v8 + 3;
  EnterCriticalSection(v8 + 3);
  if ( (a3 & 0x18) != 0 )
  {
    v27 = -2147024809;
    goto LABEL_31;
  }
  v12 = this[2];
  if ( v12[9].LockCount != -1 || v12[9].RecursionCount )
  {
    CExtBuffer::GetNextUsedItem((CExtBuffer *)1, &v20->Data1, v22);
    v13 = v27;
    if ( v27 )
    {
      v14 = 0;
      while ( 1 )
      {
        v15 = *(_DWORD **)(*((_DWORD *)v7 + 2) + 104);
        v16 = v15[6];
        if ( v13 > v16 + 8 * v15[5] - 1
          || (*(_BYTE *)(((v13 - v16) >> 3) + v15[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v13 - v16) & 7))) != 0 )
        {
          v17 = 0;
        }
        else
        {
          v17 = v15[2] + v13 * *v15;
        }
        if ( (!a3 || (a3 & *(_DWORD *)(v17 + 4)) != 0) && (*(_DWORD *)(v17 + 4) != 4 || this[2][9].LockCount != -2) )
          ++v14;
        CExtBuffer::GetNextUsedItem(0, v21, v23);
        v13 = v27;
        v7 = (CImpIRowsetUpdate *)this;
      }
    }
  }
  v18 = 1;
LABEL_38:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v18;
}

```

## disassembly

```asm
0x10033170  mov     edi, edi
0x10033172  push    ebp
0x10033173  mov     ebp, esp
0x10033175  push    0FFFFFFFFh
0x10033177  push    offset ?GetPendingRows@CImpIRowsetUpdate@@UAGJKKPAKPAPAK1@Z_SEH
0x1003317c  mov     eax, large fs:0
0x10033182  push    eax
0x10033183  sub     esp, 14h
0x10033186  push    ebx
0x10033187  push    esi
0x10033188  push    edi; unsigned int
0x10033189  mov     eax, ___security_cookie
0x1003318e  xor     eax, ebp
0x10033190  push    eax; unsigned int *
0x10033191  lea     eax, [ebp+var_C]
0x10033194  mov     large fs:0, eax
0x1003319a  xor     eax, eax
0x1003319c  push    eax; perrinfo
0x1003319d  push    eax; dwReserved
0x1003319e  mov     [ebp+var_1C], eax
0x100331a1  mov     [ebp+var_20], eax
0x100331a4  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100331aa  xor     esi, esi
0x100331ac  mov     [ebp+lpCriticalSection], esi
0x100331af  mov     eax, [ebp+arg_C]
0x100331b2  mov     [ebp+var_4], esi
0x100331b5  test    eax, eax
0x100331b7  jz      short loc_100331D1
0x100331b9  mov     [eax], esi
0x100331bb  mov     eax, [ebp+arg_10]
0x100331be  test    eax, eax
0x100331c0  jz      short loc_100331C4
0x100331c2  mov     [eax], esi
0x100331c4  mov     eax, [ebp+arg_14]
0x100331c7  test    eax, eax
0x100331c9  jz      short loc_100331D1
0x100331cb  mov     dword ptr [eax], 0
0x100331d1  mov     ebx, [ebp+this]
0x100331d4  mov     edx, [ebx+8]
0x100331d7  mov     eax, [edx+40h]
0x100331da  test    eax, eax
0x100331dc  jz      short loc_10033206
0x100331de  cmp     dword ptr [eax+10h], 1
0x100331e2  jnz     short loc_100331F2
0x100331e4  mov     ecx, [eax+8]; this
0x100331e7  test    ecx, ecx
0x100331e9  jz      short loc_100331F2
0x100331eb  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x100331f0  jmp     short loc_100331F5
0x100331f2  mov     eax, [eax+0Ch]
0x100331f5  cmp     eax, 1
0x100331f8  jnz     short loc_10033206
0x100331fa  mov     [ebp+var_10], 8000FFFFh
0x10033201  jmp     loc_1003337D
0x10033206  test    dword ptr [edx+60h], 400h
0x1003320d  jz      short loc_1003321B
0x1003320f  mov     [ebp+var_10], 80040E20h
0x10033216  jmp     loc_1003337D
0x1003321b  lea     esi, [edx+48h]
0x1003321e  push    esi; lpCriticalSection
0x1003321f  mov     [ebp+lpCriticalSection], esi
0x10033222  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10033228  test    byte ptr [ebp+arg_8], 18h
0x1003322c  jz      short loc_1003323A
0x1003322e  mov     [ebp+var_10], 80070057h
0x10033235  jmp     loc_1003337D
0x1003323a  mov     ecx, [ebx+8]
0x1003323d  cmp     dword ptr [ecx+0DCh], 0FFFFFFFFh
0x10033244  jnz     short loc_10033253
0x10033246  cmp     dword ptr [ecx+0E0h], 0
0x1003324d  jz      loc_100334BD
0x10033253  mov     ecx, [ecx+68h]
0x10033256  lea     edx, [ebp+var_10]
0x10033259  push    1; this
0x1003325b  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x10033260  mov     edi, [ebp+var_10]
0x10033263  test    edi, edi
0x10033265  jz      loc_100334BD
0x1003326b  xor     esi, esi
0x1003326d  nop     dword ptr [eax]
0x10033270  mov     eax, [ebx+8]
0x10033273  mov     ebx, [eax+68h]
0x10033276  mov     eax, [ebx+14h]
0x10033279  mov     ecx, [ebx+18h]
0x1003327c  lea     eax, ds:0FFFFFFFFh[eax*8]
0x10033283  add     eax, ecx
0x10033285  cmp     edi, eax
0x10033287  ja      short loc_100332AD
0x10033289  mov     eax, [ebx+10h]
0x1003328c  mov     edx, edi
0x1003328e  sub     edx, ecx
0x10033290  mov     ecx, edx
0x10033292  and     edx, 7
0x10033295  shr     ecx, 3
0x10033298  mov     al, [ecx+eax]
0x1003329b  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x100332a1  jnz     short loc_100332AD
0x100332a3  mov     eax, [ebx]
0x100332a5  imul    eax, edi
0x100332a8  add     eax, [ebx+8]
0x100332ab  jmp     short loc_100332AF
0x100332ad  xor     eax, eax
0x100332af  mov     ecx, [ebp+arg_8]
0x100332b2  test    ecx, ecx
0x100332b4  jz      short loc_100332BB
0x100332b6  test    [eax+4], ecx
0x100332b9  jz      short loc_100332D1
0x100332bb  cmp     dword ptr [eax+4], 4
0x100332bf  jnz     short loc_100332D0
0x100332c1  mov     ecx, [ebp+this]
0x100332c4  mov     eax, [ecx+8]
0x100332c7  cmp     dword ptr [eax+0DCh], 0FFFFFFFEh
0x100332ce  jz      short loc_100332D1
0x100332d0  inc     esi
0x100332d1  push    0; this
0x100332d3  lea     edx, [ebp+var_10]
0x100332d6  mov     ecx, ebx
0x100332d8  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x100332dd  mov     edi, [ebp+var_10]
0x100332e0  mov     ebx, [ebp+this]
0x100332e3  test    edi, edi
0x100332e5  jnz     short loc_10033270
0x100332e7  mov     [ebp+var_14], esi
0x100332ea  test    esi, esi
0x100332ec  mov     esi, [ebp+lpCriticalSection]
0x100332ef  jz      loc_100334BD
0x100332f5  cmp     [ebp+arg_C], 0
0x100332f9  jz      loc_100333E9
0x100332ff  cmp     [ebp+arg_10], 0
0x10033303  mov     ebx, [ebp+var_14]
0x10033306  jz      short loc_10033342
0x10033308  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1003330e  mov     eax, [ecx]
0x10033310  mov     edi, [eax+0Ch]
0x10033313  lea     eax, ds:0[ebx*4]
0x1003331a  push    eax
0x1003331b  push    ecx
0x1003331c  mov     ecx, edi
0x1003331e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10033324  call    edi
0x10033326  mov     edi, [ebp+arg_10]
0x10033329  mov     [edi], eax
0x1003332b  test    eax, eax
0x1003332d  jnz     short loc_1003333B
0x1003332f  mov     ebx, [ebp+this]
0x10033332  mov     [ebp+var_10], 8007000Eh
0x10033339  jmp     short loc_10033380
0x1003333b  mov     [ebp+var_1C], 1
0x10033342  cmp     [ebp+arg_14], 0
0x10033346  jz      loc_100333E9
0x1003334c  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10033352  mov     eax, [ecx]
0x10033354  mov     edi, [eax+0Ch]
0x10033357  lea     eax, ds:0[ebx*4]
0x1003335e  push    eax
0x1003335f  push    ecx
0x10033360  mov     ecx, edi
0x10033362  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10033368  call    edi
0x1003336a  mov     ecx, [ebp+arg_14]
0x1003336d  mov     [ecx], eax
0x1003336f  test    eax, eax
0x10033371  jnz     short loc_100333E9
0x10033373  mov     ebx, [ebp+this]
0x10033376  mov     [ebp+var_10], 8007000Eh
0x1003337d  mov     edi, [ebp+arg_10]
0x10033380  mov     eax, [ebx+8]
0x10033383  mov     ebx, [ebp+var_10]
0x10033386  mov     eax, [eax+38h]
0x10033389  cmp     ebx, 8007000Eh
0x1003338f  jz      short loc_100333B6
0x10033391  push    3
0x10033393  push    4
0x10033395  lea     ecx, [ebp+var_20]
0x10033398  push    ecx
0x10033399  push    dword ptr [eax+14h]
0x1003339c  push    dword ptr [eax+10h]
0x1003339f  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100333a5  test    eax, eax
0x100333a7  jnz     short loc_100333B6
0x100333a9  push    eax; int
0x100333aa  push    offset _IID_IRowsetUpdate; int
0x100333af  mov     edx, ebx
0x100333b1  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100333b6  cmp     [ebp+var_1C], 0
0x100333ba  jz      loc_100334C2
0x100333c0  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x100333c5  test    eax, eax
0x100333c7  jz      short loc_100333DB
0x100333c9  mov     ecx, [eax]
0x100333cb  push    dword ptr [edi]
0x100333cd  push    eax
0x100333ce  mov     edi, [ecx+14h]
0x100333d1  mov     ecx, edi
0x100333d3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100333d9  call    edi
0x100333db  mov     eax, [ebp+arg_10]
0x100333de  mov     dword ptr [eax], 0
0x100333e4  jmp     loc_100334C2
0x100333e9  mov     ebx, [ebp+this]
0x100333ec  lea     edx, [ebp+var_10]
0x100333ef  push    1; this
0x100333f1  mov     ecx, [ebx+8]
0x100333f4  mov     ecx, [ecx+68h]
0x100333f7  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x100333fc  cmp     [ebp+var_14], 0
0x10033400  jbe     loc_100334AD
0x10033406  xor     esi, esi
0x10033408  nop     dword ptr [eax+eax+00000000h]
0x10033410  mov     edi, [ebp+var_10]
0x10033413  test    edi, edi
0x10033415  jz      loc_100334A7
0x1003341b  mov     eax, [ebx+8]
0x1003341e  mov     ebx, [eax+68h]
0x10033421  mov     eax, [ebx+14h]
0x10033424  mov     ecx, [ebx+18h]
0x10033427  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1003342e  add     eax, ecx
0x10033430  cmp     edi, eax
0x10033432  ja      short loc_10033458
0x10033434  mov     eax, [ebx+10h]
0x10033437  mov     edx, edi
0x10033439  sub     edx, ecx
0x1003343b  mov     ecx, edx
0x1003343d  and     edx, 7
0x10033440  shr     ecx, 3
0x10033443  mov     al, [ecx+eax]
0x10033446  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1003344c  jnz     short loc_10033458
0x1003344e  mov     edx, [ebx]
0x10033450  imul    edx, edi
0x10033453  add     edx, [ebx+8]
0x10033456  jmp     short loc_1003345A
0x10033458  xor     edx, edx
0x1003345a  mov     eax, [ebp+arg_8]
0x1003345d  test    eax, eax
0x1003345f  jz      short loc_10033466
0x10033461  test    [edx+4], eax
0x10033464  jz      short loc_1003348B
0x10033466  cmp     [ebp+arg_C], 0
0x1003346a  jz      short loc_1003348A
0x1003346c  mov     eax, [ebp+arg_10]
0x1003346f  test    eax, eax
0x10033471  jz      short loc_1003347B
0x10033473  inc     dword ptr [edx+8]
0x10033476  mov     eax, [eax]
0x10033478  mov     [eax+esi*4], edi
0x1003347b  mov     eax, [ebp+arg_14]
0x1003347e  test    eax, eax
0x10033480  jz      short loc_1003348A
0x10033482  mov     ecx, [eax]
0x10033484  mov     eax, [edx+4]
0x10033487  mov     [ecx+esi*4], eax
0x1003348a  inc     esi
0x1003348b  mov     ebx, [ebp+this]
0x1003348e  lea     edx, [ebp+var_10]
0x10033491  push    0; this
0x10033493  mov     ecx, [ebx+8]
0x10033496  mov     ecx, [ecx+68h]
0x10033499  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x1003349e  cmp     esi, [ebp+var_14]
0x100334a1  jb      loc_10033410
0x100334a7  mov     [ebp+var_20], esi
0x100334aa  mov     esi, [ebp+lpCriticalSection]
0x100334ad  mov     ecx, [ebp+arg_C]
0x100334b0  xor     ebx, ebx
0x100334b2  test    ecx, ecx
0x100334b4  jz      short loc_100334C2
0x100334b6  mov     eax, [ebp+var_20]
0x100334b9  mov     [ecx], eax
0x100334bb  jmp     short loc_100334C2
0x100334bd  mov     ebx, 1
0x100334c2  test    esi, esi
0x100334c4  jz      short loc_100334CD
0x100334c6  push    esi; lpCriticalSection
0x100334c7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100334cd  mov     eax, ebx
0x100334cf  mov     ecx, [ebp+var_C]
0x100334d2  mov     large fs:0, ecx
0x100334d9  pop     ecx
0x100334da  pop     edi
0x100334db  pop     esi
0x100334dc  pop     ebx
0x100334dd  mov     esp, ebp
0x100334df  pop     ebp
0x100334e0  retn    18h
0x1004edd0  lea     ecx, [ebp+lpCriticalSection]; this
0x1004edd3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004eddd  nop
0x1004edde  nop
0x1004eddf  mov     edx, [esp-4+arg_4]
0x1004ede3  lea     eax, [edx+0Ch]
0x1004ede6  mov     ecx, [edx-24h]
0x1004ede9  xor     ecx, eax; StackCookie
0x1004edeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004edf0  mov     eax, offset stru_1004FFAC
0x1004edf5  jmp     ___CxxFrameHandler3
```
