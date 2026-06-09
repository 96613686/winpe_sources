# CBackgroundSyncHandler::_LogFailure(IUnknown *,long)

- ea: `0x1800242c4`
- end: `0x1800243ef`
- name: `?_LogFailure@CBackgroundSyncHandler@@AEAAJPEAUIUnknown@@J@Z`
- size: `299`
- prototype: `__int64 __fastcall(CBackgroundSyncHandler *__hidden this, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022e70`

## callees

- `0x180013dfc`
- `0x1800242c4`
- `0x1800245e4`
- `0x180024930`
- `0x18003fe40`
- `0x18004bf68`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x180024334`
- `SHELL32!__imp_GUIDFromStringW` at `0x180024334`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800243b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800243b1`

## pseudocode

```c
__int64 __fastcall CBackgroundSyncHandler::_LogFailure(CBackgroundSyncHandler *this, struct IUnknown *a2, int a3)
{
  int v3; // edi
  unsigned int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  CSyncItemLog *v11; // rcx
  unsigned __int16 *v12; // rsi
  const unsigned __int16 *v14; // [rsp+20h] [rbp-58h]
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  struct IOfflineFilesSyncItem *v16; // [rsp+38h] [rbp-40h] BYREF
  struct _GUID v17; // [rsp+40h] [rbp-38h] BYREF

  v3 = 0;
  if ( !*((_BYTE *)this + 104) )
  {
    CBackgroundSyncHandler::_WaitOnMutex(this, (int *)a2);
    v7 = *((_DWORD *)this + 31);
    v8 = 0;
    if ( v7 )
    {
      while ( *(struct IUnknown **)(*((_QWORD *)this + 16) + 8 * v8) != a2 )
      {
        v8 = (unsigned int)(v8 + 1);
        if ( (unsigned int)v8 >= v7 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      if ( (unsigned int)v8 >= v7 )
      {
LABEL_12:
        CBackgroundSyncHandler::_ReleaseMutex(this);
        return (unsigned int)v3;
      }
    }
    v9 = (unsigned int)v8;
    v10 = *((_QWORD *)this + 14);
    v17 = 0;
    if ( (unsigned int)GUIDFromStringW(*(_QWORD *)(v10 + 8 * v9), &v17) )
    {
      v11 = (CSyncItemLog *)*((_QWORD *)this + 11);
      pv = 0;
      v16 = 0;
      v3 = CSyncItemLog::QueryEntryByID(v11, &v17, (unsigned __int16 **)&pv, &v16, v14);
      if ( v3 >= 0 )
      {
        v12 = (unsigned __int16 *)pv;
        if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            (unsigned int)WPP_3c36ce0365fd31c693348338c0440b42_Traceguids,
            (_DWORD)pv,
            a3);
        }
        CscEvt_BGSyncFailedOnScope(v12, a3);
        CoTaskMemFree(v12);
        (*(void (__fastcall **)(struct IOfflineFilesSyncItem *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    goto LABEL_12;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800242c4  mov     [rsp+arg_8], rbx
0x1800242c9  push    rbp
0x1800242ca  push    rsi
0x1800242cb  push    rdi
0x1800242cc  sub     rsp, 60h
0x1800242d0  mov     rax, cs:__security_cookie
0x1800242d7  xor     rax, rsp
0x1800242da  mov     [rsp+78h+var_28], rax
0x1800242df  xor     edi, edi
0x1800242e1  mov     ebp, r8d
0x1800242e4  mov     rsi, rdx
0x1800242e7  mov     rbx, rcx
0x1800242ea  cmp     [rcx+68h], dil
0x1800242ee  jnz     loc_1800243D0
0x1800242f4  call    ?_WaitOnMutex@CBackgroundSyncHandler@@AEAAJPEAH@Z; CBackgroundSyncHandler::_WaitOnMutex(int *)
0x1800242f9  mov     edx, [rbx+7Ch]
0x1800242fc  xor     ecx, ecx
0x1800242fe  test    edx, edx
0x180024300  jz      short loc_180024315
0x180024302  mov     r8, [rbx+80h]
0x180024309  cmp     [r8+rcx*8], rsi
0x18002430d  jz      short loc_18002431D
0x18002430f  inc     ecx
0x180024311  cmp     ecx, edx
0x180024313  jb      short loc_180024309
0x180024315  cmp     ecx, edx
0x180024317  jnb     loc_1800243C8
0x18002431d  mov     eax, ecx
0x18002431f  lea     rdx, [rsp+78h+var_38]
0x180024324  mov     rcx, [rbx+70h]
0x180024328  xorps   xmm0, xmm0
0x18002432b  movups  xmmword ptr [rsp+78h+var_38.Data1], xmm0
0x180024330  mov     rcx, [rcx+rax*8]
0x180024334  call    cs:__imp_GUIDFromStringW
0x18002433a  test    eax, eax
0x18002433c  jz      loc_1800243C8
0x180024342  mov     rcx, [rbx+58h]; this
0x180024346  lea     r9, [rsp+78h+var_40]; struct IOfflineFilesSyncItem **
0x18002434b  lea     r8, [rsp+78h+pv]; unsigned __int16 **
0x180024350  mov     [rsp+78h+pv], rdi
0x180024355  lea     rdx, [rsp+78h+var_38]; struct _GUID *
0x18002435a  mov     [rsp+78h+var_40], rdi
0x18002435f  call    ?QueryEntryByID@CSyncItemLog@@QEAAJPEAU_GUID@@PEAPEAGPEAPEAUIOfflineFilesSyncItem@@PEBG@Z; CSyncItemLog::QueryEntryByID(_GUID *,ushort * *,IOfflineFilesSyncItem * *,ushort const *)
0x180024364  mov     edi, eax
0x180024366  test    eax, eax
0x180024368  js      short loc_1800243C8
0x18002436a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024371  lea     rax, WPP_GLOBAL_Control
0x180024378  mov     rsi, [rsp+78h+pv]
0x18002437d  cmp     rcx, rax
0x180024380  jz      short loc_1800243A4
0x180024382  test    byte ptr [rcx+1Ch], 2
0x180024386  jz      short loc_1800243A4
0x180024388  mov     rcx, [rcx+10h]
0x18002438c  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x180024393  mov     edx, 22h ; '"'
0x180024398  mov     [rsp+78h+var_58], ebp
0x18002439c  mov     r9, rsi
0x18002439f  call    WPP_SF_Sd
0x1800243a4  mov     edx, ebp; int
0x1800243a6  mov     rcx, rsi; unsigned __int16 *
0x1800243a9  call    ?CscEvt_BGSyncFailedOnScope@@YAKPEBGJ@Z; CscEvt_BGSyncFailedOnScope(ushort const *,long)
0x1800243ae  mov     rcx, rsi; pv
0x1800243b1  call    cs:__imp_CoTaskMemFree
0x1800243b7  mov     rcx, [rsp+78h+var_40]
0x1800243bc  mov     rax, [rcx]
0x1800243bf  mov     rax, [rax+10h]
0x1800243c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243c8  mov     rcx, rbx; this
0x1800243cb  call    ?_ReleaseMutex@CBackgroundSyncHandler@@AEAAXXZ; CBackgroundSyncHandler::_ReleaseMutex(void)
0x1800243d0  mov     eax, edi
0x1800243d2  mov     rcx, [rsp+78h+var_28]
0x1800243d7  xor     rcx, rsp; StackCookie
0x1800243da  call    __security_check_cookie
0x1800243df  mov     rbx, [rsp+78h+arg_8]
0x1800243e7  add     rsp, 60h
0x1800243eb  pop     rdi
0x1800243ec  pop     rsi
0x1800243ed  pop     rbp
0x1800243ee  retn
```
