# CDimInterface::NotifyOfReachabilityChange(bool,_UNREACHABILITY_REASON)

- ea: `0x18001e788`
- end: `0x18001eed9`
- name: `?NotifyOfReachabilityChange@CDimInterface@@QEAAX_NW4_UNREACHABILITY_REASON@@@Z`
- size: `1873`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003800`
- `0x1800042a8`
- `0x180007870`
- `0x1800091dc`
- `0x18001baa0`
- `0x18001eee0`
- `0x180026620`
- `0x180026704`

## callees

- `0x18000df70`
- `0x18001e788`
- `0x1800219f4`
- `0x18002e664`
- `0x18002e6d8`
- `0x180033e90`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `rtutils!RouterLogEventW` at `0x18001ea42`
- `rtutils!RouterLogEventW` at `0x18001ee8a`
- `rtutils!RouterLogEventW` at `0x18001ea42`
- `rtutils!RouterLogEventW` at `0x18001ee8a`

## string_xrefs

- `0x18001e8ae`: `Notifying Protocol = 0x%x, Interface is Reachable`
- `0x18001e934`: `Notifying Protocol = 0x%x,Interface is UnReachable=%d`
- `0x18001ed7f`: `Interface %s is unreachable because the connection attempt failed.`
- `0x18001ec87`: `Interface %s is unreachable because the Routing and RemoteACcess service is in a  paused state.`
- `0x18001ec0b`: `Interface %s is unreachable because it is not allowed to connect at this time. Check the dial-out hours configured on this interface.`
- `0x18001eb13`: `Interface %s is unreachable because the network card for this interface has been  removed.`

## pseudocode

```c
__int64 __fastcall CDimInterface::NotifyOfReachabilityChange(__int64 a1, char a2, unsigned int a3)
{
  CDimRouterManager *v6; // rcx
  WCHAR *v7; // r12
  _QWORD *v8; // rdi
  _QWORD *v9; // rbx
  __int64 v10; // rax
  __int128 *v11; // r9
  __int64 v12; // rax
  __int128 *v13; // r9
  _QWORD *i; // rax
  __int64 v15; // rax
  __int128 *v16; // r9
  unsigned int v17; // esi
  unsigned int v18; // esi
  unsigned int v19; // esi
  unsigned int v20; // esi
  unsigned int v21; // esi
  __int64 v22; // rax
  __int128 *v23; // r9
  DWORD v24; // ebx
  __int64 v25; // rax
  __int128 *v26; // r9
  __int64 v27; // rax
  __int128 *v28; // r9
  __int64 v29; // rax
  __int128 *v30; // r9
  __int64 v31; // rax
  __int128 *v32; // r9
  __int64 v33; // rax
  __int128 *v34; // r9
  __int64 v35; // rax
  __int128 *v36; // r9
  __int64 result; // rax
  int v38; // [rsp+30h] [rbp-D0h]
  LPWSTR plpszSubStringArray[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v40; // [rsp+48h] [rbp-B8h] BYREF
  GUID ActivityId; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  __int128 v43; // [rsp+6Ch] [rbp-94h]
  __int128 v44; // [rsp+7Ch] [rbp-84h]
  int v45; // [rsp+8Ch] [rbp-74h]
  _OWORD v46[3]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v47[30]; // [rsp+C0h] [rbp-40h]
  __int16 v48; // [rsp+DEh] [rbp-22h]
  int v49; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v50[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v46[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  *(_OWORD *)plpszSubStringArray = 0;
  v46[2] = *(_OWORD *)L"000-0000-000000000000}";
  v48 = 0;
  v46[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v47 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v47[14] = *(_OWORD *)L"000000}";
  v49 = 0;
  v40 = 0;
  ActivityId = 0;
  memset_0(v50, 0, sizeof(v50));
  v42 = 0;
  v45 = 0;
  v43 = 0;
  v44 = 0;
  v38 = SetActivityId((LPGUID)(a1 + 3104));
  (**(void (__fastcall ***)(__int64))a1)(a1);
  v7 = (WCHAR *)(a1 + 48);
  if ( *(_QWORD *)(a1 + 72) >= 8u )
    v7 = *(WCHAR **)v7;
  v8 = *(_QWORD **)(a1 + 272);
  v9 = (_QWORD *)*v8;
  while ( v9 != v8 )
  {
    if ( (unsigned __int64)(v9[4] - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( a2 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
        {
          LOWORD(v49) = 0;
          LOWORD(v42) = 0;
          FormatRRASErrorString(&v49, L"Notifying Protocol = 0x%x, Interface is Reachable", *((unsigned int *)v9 + 6));
          if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
            v11 = &v40;
            if ( a1 != -3104 )
              LODWORD(v11) = a1 + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminInfo,
              (unsigned int)&v49,
              (_DWORD)v11,
              v10,
              (__int64)&v42);
          }
        }
        CDimRouterManager::InterfaceReachable(v6, *((_DWORD *)v9 + 6), (void *)v9[4]);
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
        {
          LOWORD(v49) = 0;
          LOWORD(v42) = 0;
          FormatRRASErrorString(
            &v49,
            L"Notifying Protocol = 0x%x,Interface is UnReachable=%d",
            *((unsigned int *)v9 + 6),
            a3);
          if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
            v13 = &v40;
            if ( a1 != -3104 )
              LODWORD(v13) = a1 + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminInfo,
              (unsigned int)&v49,
              (_DWORD)v13,
              v12,
              (__int64)&v42);
          }
        }
        CDimRouterManager::InterfaceNotReachable(v6, *((unsigned int *)v9 + 6), v9[4], a3);
      }
    }
    if ( !*((_BYTE *)v9 + 49) )
    {
      v6 = (CDimRouterManager *)v9[2];
      if ( *((_BYTE *)v6 + 49) )
      {
        for ( i = (_QWORD *)v9[1]; !*((_BYTE *)i + 49) && v9 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
          v9 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(v6);
      }
      v9 = i;
    }
  }
  MprConvertGuidToString(a1 + 3104, 40, v46);
  plpszSubStringArray[1] = v7;
  plpszSubStringArray[0] = (LPWSTR)v46;
  if ( a2 )
  {
    if ( (unsigned int)dword_180070F40 > 2 )
      RouterLogEventW(hLogHandle, 4u, 0x4EDAu, 2u, plpszSubStringArray, 0);
    if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
    {
      LOWORD(v49) = 0;
      LOWORD(v42) = 0;
      FormatRRASErrorString(&v49, L"Interface %s is now reachable", v7);
      if ( (Microsoft_Windows_RRASEnableBits & 2) != 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
        v16 = &v40;
        if ( a1 != -3104 )
          LODWORD(v16) = a1 + 3104;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceAdminInfo,
          (unsigned int)&v49,
          (_DWORD)v16,
          v15,
          (__int64)&v42);
      }
    }
  }
  else
  {
    if ( a3 )
    {
      v17 = a3 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            v20 = v19 - 1;
            if ( v20 )
            {
              v21 = v20 - 1;
              if ( v21 )
              {
                if ( v21 != 1 )
                  goto LABEL_85;
                if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                {
                  LOWORD(v49) = 0;
                  LOWORD(v42) = 0;
                  FormatRRASErrorString(
                    &v49,
                    L"Interface %s is unreachable because the network card for this interface has been  removed.",
                    v7);
                  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                  {
                    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
                    v23 = &v40;
                    if ( a1 != -3104 )
                      LODWORD(v23) = a1 + 3104;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasDimParamTraceAdminError,
                      (unsigned int)&v49,
                      (_DWORD)v23,
                      v22,
                      (__int64)&v42);
                  }
                }
                v24 = 20185;
              }
              else
              {
                if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                {
                  LOWORD(v49) = 0;
                  LOWORD(v42) = 0;
                  FormatRRASErrorString(
                    &v49,
                    L"Interface %s is unreachable because it is not currently connected to the network.",
                    v7);
                  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                  {
                    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
                    v26 = &v40;
                    if ( a1 != -3104 )
                      LODWORD(v26) = a1 + 3104;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasDimParamTraceAdminError,
                      (unsigned int)&v49,
                      (_DWORD)v26,
                      v25,
                      (__int64)&v42);
                  }
                }
                v24 = 20184;
              }
            }
            else
            {
              if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
              {
                LOWORD(v49) = 0;
                LOWORD(v42) = 0;
                FormatRRASErrorString(
                  &v49,
                  L"Interface %s is unreachable because it is not allowed to connect at this time. Check the dial-out hour"
                   "s configured on this interface.",
                  v7);
                if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
                {
                  v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
                  v28 = &v40;
                  if ( a1 != -3104 )
                    LODWORD(v28) = a1 + 3104;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasDimParamTraceAdminError,
                    (unsigned int)&v49,
                    (_DWORD)v28,
                    v27,
                    (__int64)&v42);
                }
              }
              v24 = 20183;
            }
          }
          else
          {
            if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
            {
              LOWORD(v49) = 0;
              LOWORD(v42) = 0;
              FormatRRASErrorString(
                &v49,
                L"Interface %s is unreachable because the Routing and RemoteACcess service is in a  paused state.",
                v7);
              if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
              {
                v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
                v30 = &v40;
                if ( a1 != -3104 )
                  LODWORD(v30) = a1 + 3104;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDimParamTraceAdminError,
                  (unsigned int)&v49,
                  (_DWORD)v30,
                  v29,
                  (__int64)&v42);
              }
            }
            v24 = 20182;
          }
        }
        else
        {
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            LOWORD(v49) = 0;
            LOWORD(v42) = 0;
            FormatRRASErrorString(
              &v49,
              L"Interface %s is unreachable because it has been administratively disabled.",
              v7);
            if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
            {
              v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
              v32 = &v40;
              if ( a1 != -3104 )
                LODWORD(v32) = a1 + 3104;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceAdminError,
                (unsigned int)&v49,
                (_DWORD)v32,
                v31,
                (__int64)&v42);
            }
          }
          v24 = 20181;
        }
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v49) = 0;
          LOWORD(v42) = 0;
          FormatRRASErrorString(&v49, L"Interface %s is unreachable because the connection attempt failed.", v7);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
            v34 = &v40;
            if ( a1 != -3104 )
              LODWORD(v34) = a1 + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)&v49,
              (_DWORD)v34,
              v33,
              (__int64)&v42);
          }
        }
        v24 = 20180;
      }
    }
    else
    {
      v24 = 20179;
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v49) = 0;
        LOWORD(v42) = 0;
        FormatRRASErrorString(
          &v49,
          L"Interface %s is unreachable because there are no modems (or other connecting devices)  available for use by this interface.",
          v7);
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 280LL))(a1);
          v36 = &v40;
          if ( a1 != -3104 )
            LODWORD(v36) = a1 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceAdminError,
            (unsigned int)&v49,
            (_DWORD)v36,
            v35,
            (__int64)&v42);
        }
      }
    }
    if ( (unsigned int)dword_180070F40 > 2 )
      RouterLogEventW(hLogHandle, 4u, v24, 2u, plpszSubStringArray, 0);
  }
LABEL_85:
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( v38 )
    return ReSetActivityId(&ActivityId);
  return result;
}

```

## disassembly

```asm
0x18001e788  mov     [rsp-8+arg_8], rbx
0x18001e78d  push    rbp
0x18001e78e  push    rsi
0x18001e78f  push    rdi
0x18001e790  push    r12
0x18001e792  push    r13
0x18001e794  push    r14
0x18001e796  push    r15
0x18001e798  lea     rbp, [rsp-7F0h]
0x18001e7a0  sub     rsp, 8F0h
0x18001e7a7  mov     rax, cs:__security_cookie
0x18001e7ae  xor     rax, rsp
0x18001e7b1  mov     [rbp+820h+var_40], rax
0x18001e7b8  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18001e7bf  xorps   xmm0, xmm0
0x18001e7c2  movaps  [rbp+820h+var_890], xmm1
0x18001e7c6  xor     eax, eax
0x18001e7c8  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18001e7cf  mov     esi, r8d
0x18001e7d2  movups  xmmword ptr [rsp+920h+var_8E8], xmm0
0x18001e7d7  mov     r13b, dl
0x18001e7da  mov     r14, rcx
0x18001e7dd  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18001e7e4  lea     rcx, [rbp+820h+var_83C]; void *
0x18001e7e8  movaps  [rbp+820h+var_870], xmm1
0x18001e7ec  xor     edx, edx; Val
0x18001e7ee  movups  xmm1, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18001e7f5  mov     r8d, 7FCh; Size
0x18001e7fb  mov     [rbp+820h+var_842], ax
0x18001e7ff  movaps  [rbp+820h+var_880], xmm0
0x18001e803  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18001e80a  movaps  xmmword ptr [rbp+820h+var_860], xmm0
0x18001e80e  xorps   xmm0, xmm0
0x18001e811  movups  xmmword ptr [rbp+820h+var_860+0Eh], xmm1
0x18001e815  mov     [rbp+820h+var_840], eax
0x18001e818  xorps   xmm1, xmm1
0x18001e81b  movups  [rsp+920h+var_8D8], xmm1
0x18001e820  movups  xmmword ptr [rsp+920h+ActivityId.Data1], xmm0
0x18001e825  call    memset_0
0x18001e82a  xor     eax, eax
0x18001e82c  lea     r15, [r14+0C20h]
0x18001e833  xorps   xmm0, xmm0
0x18001e836  mov     [rsp+920h+var_8B8], eax
0x18001e83a  mov     rcx, r15; ActivityId
0x18001e83d  mov     [rbp+820h+var_894], eax
0x18001e840  lea     rdx, [rsp+920h+ActivityId]
0x18001e845  movups  [rsp+920h+var_8B4], xmm0
0x18001e84a  movups  [rsp+920h+var_8A4], xmm0
0x18001e84f  call    SetActivityId
0x18001e854  mov     rcx, [r14]
0x18001e857  mov     [rsp+920h+var_8F0], eax
0x18001e85b  mov     rax, [rcx]
0x18001e85e  mov     rcx, r14
0x18001e861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e866  lea     r12, [r14+30h]
0x18001e86a  cmp     qword ptr [r12+18h], 8
0x18001e870  jb      short loc_18001E876
0x18001e872  mov     r12, [r12]
0x18001e876  mov     rdi, [r14+110h]
0x18001e87d  mov     rbx, [rdi]
0x18001e880  cmp     rbx, rdi
0x18001e883  jz      loc_18001E9EC
0x18001e889  mov     rax, [rbx+20h]
0x18001e88d  dec     rax
0x18001e890  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e894  ja      loc_18001E9B0
0x18001e89a  test    r13b, r13b
0x18001e89d  jz      loc_18001E929
0x18001e8a3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x18001e8aa  jz      short loc_18001E918
0x18001e8ac  xor     eax, eax
0x18001e8ae  lea     rdx, aNotifyingProto; "Notifying Protocol = 0x%x, Interface is"...
0x18001e8b5  mov     word ptr [rbp+820h+var_840], ax
0x18001e8b9  lea     rcx, [rbp+820h+var_840]
0x18001e8bd  mov     word ptr [rsp+920h+var_8B8], ax
0x18001e8c2  mov     r8d, [rbx+18h]
0x18001e8c6  call    FormatRRASErrorString
0x18001e8cb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x18001e8d2  jz      short loc_18001E918
0x18001e8d4  mov     rax, [r14]
0x18001e8d7  mov     rcx, r14
0x18001e8da  mov     rax, [rax+118h]
0x18001e8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8e6  test    r15, r15
0x18001e8e9  lea     rcx, [rsp+920h+var_8B8]
0x18001e8ee  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001e8f3  lea     r9, [rsp+920h+var_8D8]
0x18001e8f8  cmovnz  r9, r15
0x18001e8fc  mov     [rsp+920h+plpszSubStringArray], rax
0x18001e901  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e908  lea     r8, [rbp+820h+var_840]
0x18001e90c  lea     rdx, RasDimParamTraceAdminInfo
0x18001e913  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e918  mov     r8, [rbx+20h]; void *
0x18001e91c  mov     edx, [rbx+18h]; unsigned int
0x18001e91f  call    ?InterfaceReachable@CDimRouterManager@@QEAAKKPEAX@Z; CDimRouterManager::InterfaceReachable(ulong,void *)
0x18001e924  jmp     loc_18001E9B0
0x18001e929  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x18001e930  jz      short loc_18001E9A1
0x18001e932  xor     eax, eax
0x18001e934  lea     rdx, aNotifyingProto_0; "Notifying Protocol = 0x%x,Interface is "...
0x18001e93b  mov     word ptr [rbp+820h+var_840], ax
0x18001e93f  lea     rcx, [rbp+820h+var_840]
0x18001e943  mov     word ptr [rsp+920h+var_8B8], ax
0x18001e948  mov     r9d, esi
0x18001e94b  mov     r8d, [rbx+18h]
0x18001e94f  call    FormatRRASErrorString
0x18001e954  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 2
0x18001e95b  jz      short loc_18001E9A1
0x18001e95d  mov     rax, [r14]
0x18001e960  mov     rcx, r14
0x18001e963  mov     rax, [rax+118h]
0x18001e96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e96f  test    r15, r15
0x18001e972  lea     rcx, [rsp+920h+var_8B8]
0x18001e977  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001e97c  lea     r9, [rsp+920h+var_8D8]
0x18001e981  cmovnz  r9, r15
0x18001e985  mov     [rsp+920h+plpszSubStringArray], rax
0x18001e98a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e991  lea     r8, [rbp+820h+var_840]
0x18001e995  lea     rdx, RasDimParamTraceAdminInfo
0x18001e99c  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e9a1  mov     r8, [rbx+20h]
0x18001e9a5  mov     r9d, esi
0x18001e9a8  mov     edx, [rbx+18h]
0x18001e9ab  call    ?InterfaceNotReachable@CDimRouterManager@@QEAAKKPEAXW4_UNREACHABILITY_REASON@@@Z; CDimRouterManager::InterfaceNotReachable(ulong,void *,_UNREACHABILITY_REASON)
0x18001e9b0  cmp     byte ptr [rbx+31h], 0
0x18001e9b4  jnz     loc_18001E880
0x18001e9ba  mov     rcx, [rbx+10h]
0x18001e9be  cmp     byte ptr [rcx+31h], 0
0x18001e9c2  jnz     short loc_18001E9CB
0x18001e9c4  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x18001e9c9  jmp     short loc_18001E9E4
0x18001e9cb  mov     rax, [rbx+8]
0x18001e9cf  jmp     short loc_18001E9DE
0x18001e9d1  cmp     rbx, [rax+10h]
0x18001e9d5  jnz     short loc_18001E9E4
0x18001e9d7  mov     rbx, rax
0x18001e9da  mov     rax, [rax+8]
0x18001e9de  cmp     byte ptr [rax+31h], 0
0x18001e9e2  jz      short loc_18001E9D1
0x18001e9e4  mov     rbx, rax
0x18001e9e7  jmp     loc_18001E880
0x18001e9ec  lea     r8, [rbp+820h+var_890]
0x18001e9f0  mov     edx, 28h ; '('
0x18001e9f5  mov     rcx, r15
0x18001e9f8  call    MprConvertGuidToString
0x18001e9fd  xor     edi, edi
0x18001e9ff  mov     [rsp+920h+var_8E8+8], r12
0x18001ea04  lea     rax, [rbp+820h+var_890]
0x18001ea08  mov     [rsp+920h+var_8E8], rax
0x18001ea0d  test    r13b, r13b
0x18001ea10  jz      loc_18001EAC5
0x18001ea16  lea     ebx, [rdi+2]
0x18001ea19  cmp     cs:dword_180070F40, ebx
0x18001ea1f  jbe     short loc_18001EA48
0x18001ea21  mov     rcx, cs:hLogHandle; hLogHandle
0x18001ea28  lea     rax, [rsp+920h+var_8E8]
0x18001ea2d  mov     [rsp+920h+dwErrorCode], edi; dwErrorCode
0x18001ea31  lea     edx, [rdi+4]; dwEventType
0x18001ea34  mov     r9d, ebx; dwSubStringCount
0x18001ea37  mov     [rsp+920h+plpszSubStringArray], rax; plpszSubStringArray
0x18001ea3c  mov     r8d, 4EDAh; dwMessageId
0x18001ea42  call    cs:__imp_RouterLogEventW
0x18001ea48  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ea4e  jz      loc_18001EE90
0x18001ea54  mov     r8, r12
0x18001ea57  mov     word ptr [rbp+820h+var_840], di
0x18001ea5b  lea     rdx, aInterfaceSIsNo; "Interface %s is now reachable"
0x18001ea62  mov     word ptr [rsp+920h+var_8B8], di
0x18001ea67  lea     rcx, [rbp+820h+var_840]
0x18001ea6b  call    FormatRRASErrorString
0x18001ea70  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001ea76  jz      loc_18001EE90
0x18001ea7c  mov     rax, [r14]
0x18001ea7f  mov     rcx, r14
0x18001ea82  mov     rax, [rax+118h]
0x18001ea89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea8e  test    r15, r15
0x18001ea91  lea     rcx, [rsp+920h+var_8B8]
0x18001ea96  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001ea9b  lea     r9, [rsp+920h+var_8D8]
0x18001eaa0  cmovnz  r9, r15
0x18001eaa4  mov     [rsp+920h+plpszSubStringArray], rax
0x18001eaa9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001eab0  lea     r8, [rbp+820h+var_840]
0x18001eab4  lea     rdx, RasDimParamTraceAdminInfo
0x18001eabb  call    McTemplateU0zjzz_EventWriteTransfer
0x18001eac0  jmp     loc_18001EE90
0x18001eac5  test    esi, esi
0x18001eac7  jz      loc_18001EDE8
0x18001eacd  sub     esi, 1
0x18001ead0  jz      loc_18001ED6F
0x18001ead6  sub     esi, 1
0x18001ead9  jz      loc_18001ECF3
0x18001eadf  sub     esi, 1
0x18001eae2  jz      loc_18001EC77
0x18001eae8  sub     esi, 1
0x18001eaeb  jz      loc_18001EBFB
0x18001eaf1  sub     esi, 1
0x18001eaf4  jz      loc_18001EB7F
0x18001eafa  cmp     esi, 1
0x18001eafd  jnz     loc_18001EE90
0x18001eb03  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001eb0a  jz      short loc_18001EB75
0x18001eb0c  mov     r8, r12
0x18001eb0f  mov     word ptr [rbp+820h+var_840], di
0x18001eb13  lea     rdx, aInterfaceSIsUn_1; "Interface %s is unreachable because the"...
0x18001eb1a  mov     word ptr [rsp+920h+var_8B8], di
0x18001eb1f  lea     rcx, [rbp+820h+var_840]
0x18001eb23  call    FormatRRASErrorString
0x18001eb28  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18001eb2f  jz      short loc_18001EB75
0x18001eb31  mov     rax, [r14]
0x18001eb34  mov     rcx, r14
0x18001eb37  mov     rax, [rax+118h]
0x18001eb3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb43  test    r15, r15
0x18001eb46  lea     rcx, [rsp+920h+var_8B8]
0x18001eb4b  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001eb50  lea     r9, [rsp+920h+var_8D8]
0x18001eb55  cmovnz  r9, r15
0x18001eb59  mov     [rsp+920h+plpszSubStringArray], rax
0x18001eb5e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001eb65  lea     r8, [rbp+820h+var_840]
0x18001eb69  lea     rdx, RasDimParamTraceAdminError
0x18001eb70  call    McTemplateU0zjzz_EventWriteTransfer
0x18001eb75  mov     ebx, 4ED9h
0x18001eb7a  jmp     loc_18001EE5F
0x18001eb7f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001eb86  jz      short loc_18001EBF1
0x18001eb88  mov     r8, r12
0x18001eb8b  mov     word ptr [rbp+820h+var_840], di
0x18001eb8f  lea     rdx, aInterfaceSIsUn; "Interface %s is unreachable because it "...
0x18001eb96  mov     word ptr [rsp+920h+var_8B8], di
0x18001eb9b  lea     rcx, [rbp+820h+var_840]
0x18001eb9f  call    FormatRRASErrorString
0x18001eba4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001ebab  jz      short loc_18001EBF1
0x18001ebad  mov     rax, [r14]
0x18001ebb0  mov     rcx, r14
0x18001ebb3  mov     rax, [rax+118h]
0x18001ebba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebbf  test    r15, r15
0x18001ebc2  lea     rcx, [rsp+920h+var_8B8]
0x18001ebc7  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001ebcc  lea     r9, [rsp+920h+var_8D8]
0x18001ebd1  cmovnz  r9, r15
0x18001ebd5  mov     [rsp+920h+plpszSubStringArray], rax
0x18001ebda  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ebe1  lea     r8, [rbp+820h+var_840]
0x18001ebe5  lea     rdx, RasDimParamTraceAdminError
0x18001ebec  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ebf1  mov     ebx, 4ED8h
0x18001ebf6  jmp     loc_18001EE5F
0x18001ebfb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001ec02  jz      short loc_18001EC6D
0x18001ec04  mov     r8, r12
0x18001ec07  mov     word ptr [rbp+820h+var_840], di
0x18001ec0b  lea     rdx, aInterfaceSIsUn_2; "Interface %s is unreachable because it "...
0x18001ec12  mov     word ptr [rsp+920h+var_8B8], di
0x18001ec17  lea     rcx, [rbp+820h+var_840]
0x18001ec1b  call    FormatRRASErrorString
0x18001ec20  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001ec27  jz      short loc_18001EC6D
0x18001ec29  mov     rax, [r14]
0x18001ec2c  mov     rcx, r14
0x18001ec2f  mov     rax, [rax+118h]
0x18001ec36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec3b  test    r15, r15
0x18001ec3e  lea     rcx, [rsp+920h+var_8B8]
0x18001ec43  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001ec48  lea     r9, [rsp+920h+var_8D8]
0x18001ec4d  cmovnz  r9, r15
0x18001ec51  mov     [rsp+920h+plpszSubStringArray], rax
0x18001ec56  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001ec5d  lea     r8, [rbp+820h+var_840]
0x18001ec61  lea     rdx, RasDimParamTraceAdminError
0x18001ec68  call    McTemplateU0zjzz_EventWriteTransfer
0x18001ec6d  mov     ebx, 4ED7h
0x18001ec72  jmp     loc_18001EE5F
0x18001ec77  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001ec7e  jz      short loc_18001ECE9
0x18001ec80  mov     r8, r12
0x18001ec83  mov     word ptr [rbp+820h+var_840], di
0x18001ec87  lea     rdx, aInterfaceSIsUn_4; "Interface %s is unreachable because the"...
0x18001ec8e  mov     word ptr [rsp+920h+var_8B8], di
0x18001ec93  lea     rcx, [rbp+820h+var_840]
0x18001ec97  call    FormatRRASErrorString
0x18001ec9c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x18001eca3  jz      short loc_18001ECE9
0x18001eca5  mov     rax, [r14]
0x18001eca8  mov     rcx, r14
0x18001ecab  mov     rax, [rax+118h]
0x18001ecb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb7  test    r15, r15
0x18001ecba  lea     rcx, [rsp+920h+var_8B8]
0x18001ecbf  mov     qword ptr [rsp+920h+dwErrorCode], rcx
0x18001ecc4  lea     r9, [rsp+920h+var_8D8]
  ... truncated ...
```
