# PushMsgAuthModule::AuthenticatePushMsg(PushMessage * const,ushort * *,ulong *)

- ea: `0x18001b0f8`
- end: `0x18001b6fa`
- name: `?AuthenticatePushMsg@PushMsgAuthModule@@QEAAJQEAVPushMessage@@PEAPEAGPEAK@Z`
- size: `1538`
- prototype: `__int64 __fastcall(PushMsgAuthModule *this, struct PushMessage *const, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016c04`

## callees

- `0x180001464`
- `0x180001694`
- `0x1800039f0`
- `0x1800043a8`
- `0x1800064a2`
- `0x18000dc6c`
- `0x18000e860`
- `0x180014bf8`
- `0x180017700`
- `0x18001946c`
- `0x18001b0f8`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b25f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b377`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b25f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b326`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b17d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b270`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b339`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b17d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b1f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b270`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b47f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b667`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b47f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b667`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b6d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b22d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b2a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b22d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b2a2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18001b3ec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18001b3ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b457`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b457`
- `DMCmnUtils!CopyString` at `0x18001b1c1`
- `DMCmnUtils!CopyString` at `0x18001b1c1`

## pseudocode

```c
__int64 __fastcall PushMsgAuthModule::AuthenticatePushMsg(
        PushMsgAuthModule *this,
        struct PushMessage *const a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  PushMsgAuthModule *v5; // r13
  int v6; // esi
  int v7; // ebx
  __int64 **v8; // r14
  int v9; // edi
  int v10; // ebx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  __int64 v13; // r13
  HLOCAL v14; // rax
  __int64 v15; // rsi
  HLOCAL v16; // rax
  int v17; // esi
  int v18; // ebx
  _DWORD *v19; // rcx
  int v20; // eax
  int v21; // ebx
  _DWORD *v22; // rcx
  __int64 v23; // rcx
  unsigned int v24; // esi
  __int64 v25; // rdi
  __int64 *v26; // rdx
  int v27; // eax
  __int64 v28; // r8
  int v29; // r9d
  unsigned __int16 *v30; // rax
  const OLECHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  PushMsgAuthModule *v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v39; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v40[2]; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v42; // [rsp+88h] [rbp-78h]
  HLOCAL v43; // [rsp+90h] [rbp-70h]
  int v44; // [rsp+98h] [rbp-68h]
  HLOCAL SenderAddress; // [rsp+A0h] [rbp-60h]
  HLOCAL v46; // [rsp+A8h] [rbp-58h]
  int v47; // [rsp+B0h] [rbp-50h]
  int v48; // [rsp+B4h] [rbp-4Ch]
  int v49; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v50)(); // [rsp+C0h] [rbp-40h]
  struct PushMessage *v51; // [rsp+C8h] [rbp-38h]
  HLOCAL v52; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL v53; // [rsp+D8h] [rbp-28h] BYREF
  HLOCAL v54; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 **v55; // [rsp+E8h] [rbp-18h]
  unsigned int *v56; // [rsp+F0h] [rbp-10h]
  GUID clsid; // [rsp+F8h] [rbp-8h] BYREF
  char *v58; // [rsp+110h] [rbp+10h] BYREF
  char v59; // [rsp+118h] [rbp+18h]
  PushMsgAuthModule **v60; // [rsp+120h] [rbp+20h]
  __int64 v61; // [rsp+128h] [rbp+28h]
  PushMsgAuthModule **v62; // [rsp+130h] [rbp+30h]
  __int64 v63; // [rsp+138h] [rbp+38h]
  const OLECHAR *v64; // [rsp+140h] [rbp+40h]
  int v65; // [rsp+148h] [rbp+48h]
  int v66; // [rsp+14Ch] [rbp+4Ch]

  v56 = a4;
  v55 = a3;
  v5 = this;
  v36 = this;
  v6 = 0;
  v39 = 0;
  memset_0(&v41, 0, 0x50u);
  clsid = 0;
  hMem = 0;
  v37 = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    goto LABEL_82;
  }
  v41 = 80;
  v40[0] = 0;
  v58 = (char *)a2 + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v59 = 1;
  v8 = (__int64 **)((char *)a2 + 8);
  v9 = -2147023728;
  if ( *((_DWORD *)a2 + 4) > 2u && (v11 = (*v8)[2]) != 0 )
  {
    if ( *(_DWORD *)v11 == 1 )
      v10 = CopyString(*(const unsigned __int16 **)(v11 + 16), 0xFFFFFFFF, v40);
    else
      v10 = -2147024883;
  }
  else
  {
    v10 = -2147023728;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v12 = 0;
  if ( v10 >= 0 )
    v12 = v40[0];
  v42 = v12;
  SenderAddress = (HLOCAL)PushMessage::GetSenderAddress(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v7 = -2147024882;
  if ( *((_DWORD *)a2 + 4) )
  {
    v13 = **v8;
    if ( v13 )
    {
      if ( *(_DWORD *)v13 == 3 )
      {
        v14 = LocalAlloc(0x40u, *(unsigned int *)(v13 + 8));
        v43 = v14;
        if ( v14 )
        {
          memcpy_0(v14, *(const void **)(v13 + 24), *(unsigned int *)(v13 + 8));
          v44 = *(_DWORD *)(v13 + 8);
        }
        else
        {
          v6 = -2147024882;
        }
      }
      else
      {
        v6 = -2147024883;
      }
    }
    else
    {
      v6 = -2147023728;
    }
    v5 = v36;
  }
  else
  {
    v6 = -2147023728;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  if ( v6 < 0 )
  {
    v7 = v6;
    goto LABEL_82;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  if ( *((_DWORD *)a2 + 4) > 8u && (v15 = (*v8)[8]) != 0 )
  {
    if ( *(_DWORD *)v15 == 3 )
    {
      v16 = LocalAlloc(0x40u, *(unsigned int *)(v15 + 8));
      v46 = v16;
      if ( v16 )
      {
        v7 = 0;
        memcpy_0(v16, *(const void **)(v15 + 24), *(unsigned int *)(v15 + 8));
        v47 = *(_DWORD *)(v15 + 8);
      }
    }
    else
    {
      v7 = -2147024883;
    }
  }
  else
  {
    v7 = -2147023728;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  if ( v7 == -2147023728 )
  {
    v46 = 0;
    v47 = 0;
  }
  else if ( v7 < 0 )
  {
    goto LABEL_82;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v17 = 0;
  if ( *((_DWORD *)a2 + 4) > 5u && (v19 = (_DWORD *)(*v8)[5]) != 0 )
  {
    if ( *v19 == 4 )
    {
      v18 = 0;
      v17 = v19[1];
    }
    else
    {
      v18 = -2147024883;
    }
  }
  else
  {
    v18 = -2147023728;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v20 = 0;
  if ( v18 >= 0 )
    v20 = v17;
  v48 = v20;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v21 = 27;
  if ( *((_DWORD *)a2 + 4) > 7u )
  {
    v22 = (_DWORD *)(*v8)[7];
    if ( v22 )
    {
      if ( *v22 == 4 )
      {
        v9 = 0;
        v21 = v22[1];
      }
      else
      {
        v9 = -2147024883;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  if ( v9 < 0 )
    v21 = 27;
  v49 = v21;
  v51 = a2;
  v50 = AttemptNotification;
  v7 = 44761098;
  v24 = 0;
  if ( !*(_DWORD *)v5 )
    goto LABEL_78;
  while ( v7 == 44761098 )
  {
    v25 = 8LL * v24;
    if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
      McTemplateU0z_EventWriteTransfer(
        v23,
        PushRouterMessageAuthenticationProviderBeingUsed,
        *(_QWORD *)(*((_QWORD *)v5 + 2) + 8LL * v24));
    if ( CLSIDFromProgID(*(LPCOLESTR *)(*((_QWORD *)v5 + 2) + 8LL * v24), &clsid) >= 0 )
    {
      if ( v39 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
        v39 = 0;
      }
      if ( CoCreateInstance(&clsid, 0, 1u, &GUID_7554d374_cb84_4d66_9f47_e8c0791147e9, &v39) >= 0 )
      {
        LocalFree(hMem);
        hMem = 0;
        v27 = (*(__int64 (__fastcall **)(LPVOID, int *, HLOCAL *, unsigned int *))(*(_QWORD *)v39 + 24LL))(
                v39,
                &v41,
                &hMem,
                &v37);
        v7 = v27;
        if ( v27 < 0 )
        {
          if ( (unsigned int)dword_180050060 > 2 )
          {
            v31 = *(const OLECHAR **)(v25 + *((_QWORD *)v5 + 2));
            LODWORD(v36) = v27;
            if ( v31 )
            {
              v32 = -1;
              do
                ++v32;
              while ( v31[v32] );
              v33 = 2 * v32 + 2;
            }
            else
            {
              v31 = &word_1800401D0;
              v33 = 2;
            }
            v64 = v31;
            v65 = v33;
            v66 = 0;
            v62 = &v36;
            v63 = 4;
            tlgWriteTransfer_EventWriteTransfer(&dword_180050060, &byte_180046877, 0);
          }
          if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
          {
            LODWORD(v36) = v7;
            v60 = &v36;
            v61 = 4;
            McGenEventWrite_EventWriteTransfer(MDM_PUSHROUTER_Context, PushRouterMessageAuthenticationFailed, v28, 2);
          }
          goto LABEL_82;
        }
        if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 2) != 0 )
          McTemplateU0zzzzdd_EventWriteTransfer(
            (_DWORD)v42,
            (unsigned int)PushRouterMessageAuthenticationSucceeded,
            *(_QWORD *)(*((_QWORD *)v5 + 2) + 8LL * v24),
            (_DWORD)hMem,
            (__int64)v42,
            (__int64)SenderAddress,
            v37,
            v27);
        if ( (unsigned int)dword_180050060 > 4 )
        {
          v52 = SenderAddress;
          v53 = v42;
          v54 = hMem;
          v58 = *(char **)(v25 + *((_QWORD *)v5 + 2));
          LODWORD(v40[0]) = v37;
          LODWORD(v36) = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v58,
            (unsigned int)&byte_1800467FF,
            v28,
            v29,
            (__int64)&v36,
            (__int64)v40,
            (__int64)&v58,
            (__int64)&v54,
            (__int64)&v53,
            (__int64)&v52);
        }
        goto LABEL_65;
      }
      v7 = 44761098;
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
      {
        v26 = PushRouterMessageAuthenticationUsingProviderFailed;
        goto LABEL_54;
      }
    }
    else
    {
      v7 = 44761098;
      if ( (Microsoft_Windows_DeviceManagement_PushrouterEnableBits & 1) != 0 )
      {
        v26 = PushRouterGettingMessageAuthenticationProviderFailed;
LABEL_54:
        McTemplateU0zd_EventWriteTransfer(v23, v26, *(_QWORD *)(*((_QWORD *)v5 + 2) + 8LL * v24), 44761098, ppv);
      }
    }
LABEL_65:
    if ( ++v24 >= *(_DWORD *)v5 )
      break;
  }
  if ( v7 >= 0 && v7 != 44761098 )
  {
    v30 = (unsigned __int16 *)hMem;
    goto LABEL_79;
  }
LABEL_78:
  LocalFree(hMem);
  v30 = 0;
LABEL_79:
  *v55 = v30;
  hMem = 0;
  *v56 = v37;
  if ( v39 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
LABEL_82:
  LocalFree(v43);
  LocalFree(v46);
  LocalFree(v42);
  LocalFree(SenderAddress);
  LocalFree(hMem);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b0f8  push    rbp
0x18001b0fa  push    rbx
0x18001b0fb  push    rsi
0x18001b0fc  push    rdi
0x18001b0fd  push    r12
0x18001b0ff  push    r13
0x18001b101  push    r14
0x18001b103  push    r15
0x18001b105  lea     rbp, [rsp-68h]
0x18001b10a  sub     rsp, 168h
0x18001b111  mov     rax, cs:__security_cookie
0x18001b118  xor     rax, rsp
0x18001b11b  mov     [rbp+0A0h+var_50], rax
0x18001b11f  mov     [rbp+0A0h+var_B0], r9
0x18001b123  mov     [rbp+0A0h+var_B8], r8
0x18001b127  mov     r12, rdx
0x18001b12a  mov     r13, rcx
0x18001b12d  mov     [rsp+1A0h+var_150], rcx
0x18001b132  xor     esi, esi
0x18001b134  mov     [rsp+1A0h+var_138], rsi
0x18001b139  lea     ebx, [rsi+50h]
0x18001b13c  mov     r8d, ebx; Size
0x18001b13f  xor     edx, edx; Val
0x18001b141  lea     rcx, [rbp+0A0h+var_120]; void *
0x18001b145  call    memset_0
0x18001b14a  xorps   xmm0, xmm0
0x18001b14d  movups  xmmword ptr [rbp+0A0h+clsid.Data1], xmm0
0x18001b151  mov     [rsp+1A0h+hMem], rsi
0x18001b156  mov     [rsp+1A0h+var_148], esi
0x18001b15a  test    r12, r12
0x18001b15d  jnz     short loc_18001B169
0x18001b15f  mov     ebx, 80004003h
0x18001b164  jmp     loc_18001B6A5
0x18001b169  mov     [rbp+0A0h+var_120], ebx
0x18001b16c  mov     [rsp+1A0h+var_130], rsi
0x18001b171  lea     r15, [r12+20h]
0x18001b176  mov     [rbp+0A0h+var_90], r15
0x18001b17a  mov     rcx, r15; lpCriticalSection
0x18001b17d  call    cs:__imp_EnterCriticalSection
0x18001b183  mov     [rbp+0A0h+var_88], 1
0x18001b187  lea     r14, [r12+8]
0x18001b18c  mov     edi, 80070490h
0x18001b191  cmp     dword ptr [r12+10h], 2
0x18001b197  ja      short loc_18001B19D
0x18001b199  mov     ebx, edi
0x18001b19b  jmp     short loc_18001B1C9
0x18001b19d  mov     rax, [r14]
0x18001b1a0  mov     rcx, [rax+10h]
0x18001b1a4  test    rcx, rcx
0x18001b1a7  jz      short loc_18001B199
0x18001b1a9  cmp     dword ptr [rcx], 1
0x18001b1ac  jz      short loc_18001B1B5
0x18001b1ae  mov     ebx, 8007000Dh
0x18001b1b3  jmp     short loc_18001B1C9
0x18001b1b5  lea     r8, [rsp+1A0h+var_130]
0x18001b1ba  or      edx, 0FFFFFFFFh
0x18001b1bd  mov     rcx, [rcx+10h]
0x18001b1c1  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001b1c7  mov     ebx, eax
0x18001b1c9  mov     rcx, r15; lpCriticalSection
0x18001b1cc  call    cs:__imp_LeaveCriticalSection
0x18001b1d2  test    ebx, ebx
0x18001b1d4  mov     rax, rsi
0x18001b1d7  js      short loc_18001B1DE
0x18001b1d9  mov     rax, [rsp+1A0h+var_130]
0x18001b1de  mov     [rbp+0A0h+var_118], rax
0x18001b1e2  mov     rcx, r12; this
0x18001b1e5  call    ?GetSenderAddress@PushMessage@@QEAAPEBGXZ; PushMessage::GetSenderAddress(void)
0x18001b1ea  mov     [rbp+0A0h+var_100], rax
0x18001b1ee  mov     rcx, r15; lpCriticalSection
0x18001b1f1  call    cs:__imp_EnterCriticalSection
0x18001b1f7  mov     ebx, 8007000Eh
0x18001b1fc  cmp     [r12+10h], esi
0x18001b201  ja      short loc_18001B207
0x18001b203  mov     esi, edi
0x18001b205  jmp     short loc_18001B25C
0x18001b207  mov     rax, [r14]
0x18001b20a  mov     r13, [rax]
0x18001b20d  test    r13, r13
0x18001b210  jnz     short loc_18001B216
0x18001b212  mov     esi, edi
0x18001b214  jmp     short loc_18001B257
0x18001b216  cmp     dword ptr [r13+0], 3
0x18001b21b  jz      short loc_18001B224
0x18001b21d  mov     esi, 8007000Dh
0x18001b222  jmp     short loc_18001B257
0x18001b224  mov     edx, [r13+8]; uBytes
0x18001b228  mov     ecx, 40h ; '@'; uFlags
0x18001b22d  call    cs:__imp_LocalAlloc
0x18001b233  mov     [rbp+0A0h+var_110], rax
0x18001b237  test    rax, rax
0x18001b23a  jnz     short loc_18001B240
0x18001b23c  mov     esi, ebx
0x18001b23e  jmp     short loc_18001B257
0x18001b240  mov     r8d, [r13+8]; Size
0x18001b244  mov     rdx, [r13+18h]; Src
0x18001b248  mov     rcx, rax; void *
0x18001b24b  call    memcpy_0
0x18001b250  mov     eax, [r13+8]
0x18001b254  mov     [rbp+0A0h+var_108], eax
0x18001b257  mov     r13, [rsp+1A0h+var_150]
0x18001b25c  mov     rcx, r15; lpCriticalSection
0x18001b25f  call    cs:__imp_LeaveCriticalSection
0x18001b265  test    esi, esi
0x18001b267  js      loc_18001B6A3
0x18001b26d  mov     rcx, r15; lpCriticalSection
0x18001b270  call    cs:__imp_EnterCriticalSection
0x18001b276  cmp     dword ptr [r12+10h], 8
0x18001b27c  ja      short loc_18001B282
0x18001b27e  mov     ebx, edi
0x18001b280  jmp     short loc_18001B2C9
0x18001b282  mov     rax, [r14]
0x18001b285  mov     rsi, [rax+40h]
0x18001b289  test    rsi, rsi
0x18001b28c  jz      short loc_18001B27E
0x18001b28e  cmp     dword ptr [rsi], 3
0x18001b291  jz      short loc_18001B29A
0x18001b293  mov     ebx, 8007000Dh
0x18001b298  jmp     short loc_18001B2C9
0x18001b29a  mov     edx, [rsi+8]; uBytes
0x18001b29d  mov     ecx, 40h ; '@'; uFlags
0x18001b2a2  call    cs:__imp_LocalAlloc
0x18001b2a8  mov     [rbp+0A0h+var_F8], rax
0x18001b2ac  test    rax, rax
0x18001b2af  jz      short loc_18001B2C9
0x18001b2b1  xor     ebx, ebx
0x18001b2b3  mov     r8d, [rsi+8]; Size
0x18001b2b7  mov     rdx, [rsi+18h]; Src
0x18001b2bb  mov     rcx, rax; void *
0x18001b2be  call    memcpy_0
0x18001b2c3  mov     eax, [rsi+8]
0x18001b2c6  mov     [rbp+0A0h+var_F0], eax
0x18001b2c9  mov     rcx, r15; lpCriticalSection
0x18001b2cc  call    cs:__imp_LeaveCriticalSection
0x18001b2d2  cmp     ebx, edi
0x18001b2d4  jnz     short loc_18001B2E7
0x18001b2d6  mov     [rbp+0A0h+var_F8], 0
0x18001b2de  mov     [rbp+0A0h+var_F0], 0
0x18001b2e5  jmp     short loc_18001B2EF
0x18001b2e7  test    ebx, ebx
0x18001b2e9  js      loc_18001B6A5
0x18001b2ef  mov     rcx, r15; lpCriticalSection
0x18001b2f2  call    cs:__imp_EnterCriticalSection
0x18001b2f8  xor     esi, esi
0x18001b2fa  cmp     dword ptr [r12+10h], 5
0x18001b300  ja      short loc_18001B306
0x18001b302  mov     ebx, edi
0x18001b304  jmp     short loc_18001B323
0x18001b306  mov     rax, [r14]
0x18001b309  mov     rcx, [rax+28h]
0x18001b30d  test    rcx, rcx
0x18001b310  jz      short loc_18001B302
0x18001b312  cmp     dword ptr [rcx], 4
0x18001b315  jz      short loc_18001B31E
0x18001b317  mov     ebx, 8007000Dh
0x18001b31c  jmp     short loc_18001B323
0x18001b31e  xor     ebx, ebx
0x18001b320  mov     esi, [rcx+4]
0x18001b323  mov     rcx, r15; lpCriticalSection
0x18001b326  call    cs:__imp_LeaveCriticalSection
0x18001b32c  xor     eax, eax
0x18001b32e  test    ebx, ebx
0x18001b330  cmovns  eax, esi
0x18001b333  mov     [rbp+0A0h+var_EC], eax
0x18001b336  mov     rcx, r15; lpCriticalSection
0x18001b339  call    cs:__imp_EnterCriticalSection
0x18001b33f  mov     esi, 1Bh
0x18001b344  mov     ebx, esi
0x18001b346  cmp     dword ptr [r12+10h], 7
0x18001b34c  ja      short loc_18001B353
0x18001b34e  xor     r14d, r14d
0x18001b351  jmp     short loc_18001B374
0x18001b353  mov     rax, [r14]
0x18001b356  mov     rcx, [rax+38h]
0x18001b35a  xor     r14d, r14d
0x18001b35d  test    rcx, rcx
0x18001b360  jz      short loc_18001B374
0x18001b362  cmp     dword ptr [rcx], 4
0x18001b365  jz      short loc_18001B36E
0x18001b367  mov     edi, 8007000Dh
0x18001b36c  jmp     short loc_18001B374
0x18001b36e  mov     edi, r14d
0x18001b371  mov     ebx, [rcx+4]
0x18001b374  mov     rcx, r15; lpCriticalSection
0x18001b377  call    cs:__imp_LeaveCriticalSection
0x18001b37d  test    edi, edi
0x18001b37f  cmovs   ebx, esi
0x18001b382  mov     [rbp+0A0h+var_E8], ebx
0x18001b385  mov     [rbp+0A0h+var_D8], r12
0x18001b389  lea     rax, AttemptNotification
0x18001b390  mov     [rbp+0A0h+var_E0], rax
0x18001b394  mov     r15d, 2AB000Ah
0x18001b39a  mov     ebx, r15d
0x18001b39d  mov     esi, r14d
0x18001b3a0  cmp     [r13+0], r14d
0x18001b3a4  jbe     loc_18001B662
0x18001b3aa  mov     r12d, 1
0x18001b3b0  cmp     ebx, r15d
0x18001b3b3  jnz     loc_18001B580
0x18001b3b9  mov     eax, esi
0x18001b3bb  lea     rdi, ds:0[rax*8]
0x18001b3c3  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x18001b3ca  jz      short loc_18001B3E0
0x18001b3cc  mov     r8, [r13+10h]
0x18001b3d0  mov     r8, [r8+rdi]
0x18001b3d4  lea     rdx, PushRouterMessageAuthenticationProviderBeingUsed
0x18001b3db  call    McTemplateU0z_EventWriteTransfer
0x18001b3e0  mov     rcx, [r13+10h]
0x18001b3e4  lea     rdx, [rbp+0A0h+clsid]; lpclsid
0x18001b3e8  mov     rcx, [rcx+rdi]; lpszProgID
0x18001b3ec  call    cs:__imp_CLSIDFromProgID
0x18001b3f2  test    eax, eax
0x18001b3f4  jns     short loc_18001B422
0x18001b3f6  mov     ebx, r15d
0x18001b3f9  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, r12b
0x18001b400  jz      loc_18001B573
0x18001b406  lea     rdx, PushRouterGettingMessageAuthenticationProviderFailed
0x18001b40d  mov     r8, [r13+10h]
0x18001b411  mov     r8, [r8+rdi]
0x18001b415  mov     r9d, r15d
0x18001b418  call    McTemplateU0zd_EventWriteTransfer
0x18001b41d  jmp     loc_18001B573
0x18001b422  mov     rcx, [rsp+1A0h+var_138]
0x18001b427  test    rcx, rcx
0x18001b42a  jz      short loc_18001B43D
0x18001b42c  mov     rax, [rcx]
0x18001b42f  mov     rax, [rax+10h]
0x18001b433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b438  mov     [rsp+1A0h+var_138], r14
0x18001b43d  lea     rax, [rsp+1A0h+var_138]
0x18001b442  mov     [rsp+1A0h+ppv], rax; ppv
0x18001b447  lea     r9, _GUID_7554d374_cb84_4d66_9f47_e8c0791147e9; riid
0x18001b44e  mov     r8d, r12d; dwClsContext
0x18001b451  xor     edx, edx; pUnkOuter
0x18001b453  lea     rcx, [rbp+0A0h+clsid]; rclsid
0x18001b457  call    cs:__imp_CoCreateInstance
0x18001b45d  test    eax, eax
0x18001b45f  jns     short loc_18001B47A
0x18001b461  mov     ebx, r15d
0x18001b464  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, r12b
0x18001b46b  jz      loc_18001B573
0x18001b471  lea     rdx, PushRouterMessageAuthenticationUsingProviderFailed
0x18001b478  jmp     short loc_18001B40D
0x18001b47a  mov     rcx, [rsp+1A0h+hMem]; hMem
0x18001b47f  call    cs:__imp_LocalFree
0x18001b485  mov     [rsp+1A0h+hMem], r14
0x18001b48a  mov     rcx, [rsp+1A0h+var_138]
0x18001b48f  mov     rax, [rcx]
0x18001b492  lea     r9, [rsp+1A0h+var_148]
0x18001b497  lea     r8, [rsp+1A0h+hMem]
0x18001b49c  lea     rdx, [rbp+0A0h+var_120]
0x18001b4a0  mov     rax, [rax+18h]
0x18001b4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a9  mov     ebx, eax
0x18001b4ab  test    eax, eax
0x18001b4ad  js      loc_18001B59B
0x18001b4b3  test    cs:Microsoft_Windows_DeviceManagement_PushrouterEnableBits, 2
0x18001b4ba  jz      short loc_18001B4F3
0x18001b4bc  mov     r8, [r13+10h]
0x18001b4c0  mov     dword ptr [rsp+1A0h+var_168], eax
0x18001b4c4  mov     ecx, [rsp+1A0h+var_148]
0x18001b4c8  mov     dword ptr [rsp+1A0h+var_170], ecx
0x18001b4cc  mov     rcx, [rbp+0A0h+var_100]
0x18001b4d0  mov     [rsp+1A0h+var_178], rcx
0x18001b4d5  mov     rcx, [rbp+0A0h+var_118]
0x18001b4d9  mov     [rsp+1A0h+ppv], rcx
0x18001b4de  mov     r9, [rsp+1A0h+hMem]
0x18001b4e3  mov     r8, [r8+rdi]
0x18001b4e7  lea     rdx, PushRouterMessageAuthenticationSucceeded
0x18001b4ee  call    McTemplateU0zzzzdd_EventWriteTransfer
0x18001b4f3  mov     eax, cs:dword_180050060
0x18001b4f9  cmp     eax, 4
0x18001b4fc  jbe     short loc_18001B573
0x18001b4fe  mov     rax, [rbp+0A0h+var_100]
0x18001b502  mov     [rbp+0A0h+var_D0], rax
0x18001b506  mov     rax, [rbp+0A0h+var_118]
0x18001b50a  mov     [rbp+0A0h+var_C8], rax
0x18001b50e  mov     rax, [rsp+1A0h+hMem]
0x18001b513  mov     [rbp+0A0h+var_C0], rax
0x18001b517  mov     rax, [r13+10h]
0x18001b51b  mov     rcx, [rdi+rax]
0x18001b51f  mov     [rbp+0A0h+var_90], rcx
0x18001b523  mov     eax, [rsp+1A0h+var_148]
0x18001b527  mov     dword ptr [rsp+1A0h+var_130], eax
0x18001b52b  mov     dword ptr [rsp+1A0h+var_150], ebx
0x18001b52f  lea     rax, [rbp+0A0h+var_D0]
0x18001b533  mov     [rsp+1A0h+var_158], rax
0x18001b538  lea     rax, [rbp+0A0h+var_C8]
0x18001b53c  mov     [rsp+1A0h+var_160], rax
0x18001b541  lea     rax, [rbp+0A0h+var_C0]
0x18001b545  mov     [rsp+1A0h+var_168], rax
0x18001b54a  lea     rax, [rbp+0A0h+var_90]
0x18001b54e  mov     [rsp+1A0h+var_170], rax
0x18001b553  lea     rax, [rsp+1A0h+var_130]
0x18001b558  mov     [rsp+1A0h+var_178], rax
0x18001b55d  lea     rax, [rsp+1A0h+var_150]
0x18001b562  mov     [rsp+1A0h+ppv], rax
0x18001b567  lea     rdx, byte_1800467FF
0x18001b56e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18001b573  add     esi, r12d
  ... truncated ...
```
