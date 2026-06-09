# UpdateRoutes

- ea: `0x18002bf1c`
- end: `0x18002c46d`
- name: `UpdateRoutes`
- size: `1361`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003de20`
- `0x18003de40`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x180011790`
- `0x18002bf1c`
- `0x18004b218`
- `0x180057c48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18002c115`
- `ntdll!RtlReleaseResource` at `0x18002c213`
- `ntdll!RtlReleaseResource` at `0x18002c36d`
- `ntdll!RtlReleaseResource` at `0x18002c3c1`
- `ntdll!RtlReleaseResource` at `0x18002c115`
- `ntdll!RtlReleaseResource` at `0x18002c213`
- `ntdll!RtlReleaseResource` at `0x18002c36d`
- `ntdll!RtlReleaseResource` at `0x18002c3c1`
- `ntdll!RtlAcquireResourceShared` at `0x18002c009`
- `ntdll!RtlAcquireResourceShared` at `0x18002c2a5`
- `ntdll!RtlAcquireResourceShared` at `0x18002c009`
- `ntdll!RtlAcquireResourceShared` at `0x18002c2a5`
- `KERNEL32!LeaveCriticalSection` at `0x18002bfaf`
- `KERNEL32!LeaveCriticalSection` at `0x18002c277`
- `KERNEL32!LeaveCriticalSection` at `0x18002c3ef`
- `KERNEL32!LeaveCriticalSection` at `0x18002bfaf`
- `KERNEL32!LeaveCriticalSection` at `0x18002c277`
- `KERNEL32!LeaveCriticalSection` at `0x18002c3ef`
- `KERNEL32!EnterCriticalSection` at `0x18002bf8f`
- `KERNEL32!EnterCriticalSection` at `0x18002c264`
- `KERNEL32!EnterCriticalSection` at `0x18002bf8f`
- `KERNEL32!EnterCriticalSection` at `0x18002c264`

## string_xrefs

- `0x18002bfc5`: `UpdateRoutes`
- `0x18002c03a`: `UpdateRoutes: Updating routes over %ws`
- `0x18002c0b4`: `UpdateRoutes: %ws is not connected.`
- `0x18002c139`: `Leaving: UpdateRoutes`
- `0x18002c23b`: `Leaving: UpdateRoutes`
- `0x18002c3d4`: `Leaving: UpdateRoutes`
- `0x18002c1b9`: `UpdateRoutes: Error %d block deleting routes`
- `0x18002c2f0`: `UpdateRoutes: %ws returned %d while trying to update routes. Trying other protocols`
- `0x18002c387`: `UpdateRoutes : No interface with ICB number %d`

## pseudocode

```c
__int64 __fastcall UpdateRoutes(unsigned int a1, __int64 a2, int a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  char v8; // cl
  __int128 *v9; // r9
  __int128 *v10; // r9
  __int128 *v11; // r9
  unsigned int v12; // esi
  unsigned int v13; // edx
  void *RtmRegistrationHandle; // rax
  unsigned int v15; // eax
  __int128 *v16; // r9
  __int128 *v17; // r9
  _QWORD *i; // r14
  __int64 (__fastcall *v20)(_QWORD); // rax
  unsigned int v21; // eax
  __int128 *v22; // r9
  __int128 v23; // [rsp+38h] [rbp-870h] BYREF
  int v24; // [rsp+48h] [rbp-860h] BYREF
  __int128 v25; // [rsp+4Ch] [rbp-85Ch]
  __int128 v26; // [rsp+5Ch] [rbp-84Ch]
  int v27; // [rsp+6Ch] [rbp-83Ch]
  int v28; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v29[2044]; // [rsp+74h] [rbp-834h] BYREF

  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  v24 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v23 = 0;
  EnterCriticalSection(&RouterStateLock);
  if ( !(_DWORD)RouterState )
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"Entered: %ws", L"UpdateRoutes");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
    }
    RtlAcquireResourceShared(&Resource, 1u);
    v6 = InterfaceLookupByICBSeqNumber(a1);
    v7 = v6;
    if ( v6 )
    {
      v8 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v28) = 0;
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v28, L"UpdateRoutes: Updating routes over %ws", *(_QWORD *)(v6 + 72));
        v8 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v9 = &v23;
          if ( v7 != -688 )
            LODWORD(v9) = v7 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v28,
            (_DWORD)v9,
            *(_QWORD *)(v7 + 72),
            (__int64)&v24);
          v8 = Microsoft_Windows_RRASEnableBits;
        }
      }
      if ( *(_DWORD *)(v7 + 168) < 4u )
      {
        if ( v8 < 0 )
        {
          LOWORD(v28) = 0;
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v28, L"UpdateRoutes: %ws is not connected.", *(_QWORD *)(v7 + 72));
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v10 = &v23;
            if ( v7 != -688 )
              LODWORD(v10) = v7 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v28,
              (_DWORD)v10,
              *(_QWORD *)(v7 + 72),
              (__int64)&v24);
          }
        }
        RtlReleaseResource(&Resource);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v24) = 0;
          v11 = &v23;
          if ( v7 != -688 )
            LODWORD(v11) = v7 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)L"Leaving: UpdateRoutes",
            (_DWORD)v11,
            *(_QWORD *)(v7 + 72),
            (__int64)&v24);
        }
        v12 = 87;
LABEL_34:
        EnterCriticalSection(&RouterStateLock);
        --HIDWORD(RouterState);
        LeaveCriticalSection(&RouterStateLock);
        return v12;
      }
      v13 = 33;
      if ( a3 != 33 )
        v13 = 87;
      RtmRegistrationHandle = (void *)GetRtmRegistrationHandle((struct _GUID *)(v7 + 688), v13, 0x2712u);
      v15 = DeleteRtmRoutes(RtmRegistrationHandle, *(_DWORD *)(v7 + 16), 0);
      v12 = v15;
      if ( v15 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v28) = 0;
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v28, L"UpdateRoutes: Error %d block deleting routes", v15);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v16 = &v23;
            if ( v7 != -688 )
              LODWORD(v16) = v7 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v28,
              (_DWORD)v16,
              *(_QWORD *)(v7 + 72),
              (__int64)&v24);
          }
        }
        RtlReleaseResource(&Resource);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v24) = 0;
          v17 = &v23;
          if ( v7 != -688 )
            LODWORD(v17) = v7 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)L"Leaving: UpdateRoutes",
            (_DWORD)v17,
            *(_QWORD *)(v7 + 72),
            (__int64)&v24);
        }
        goto LABEL_34;
      }
      if ( *(_QWORD *)(v7 + 192) )
      {
        v12 = 911;
      }
      else
      {
        v12 = 2;
        RtlAcquireResourceShared(&stru_18008C4A0, 1u);
        for ( i = *(_QWORD **)(v7 + 56); i != (_QWORD *)(v7 + 56); i = (_QWORD *)*i )
        {
          v20 = *(__int64 (__fastcall **)(_QWORD))(i[3] + 176LL);
          if ( v20 )
          {
            v21 = v20(*(unsigned int *)(v7 + 16));
            v12 = v21;
            if ( !v21 || v21 == 600 )
            {
              v12 = 600;
              *(_QWORD *)(v7 + 192) = a2;
              break;
            }
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v28) = 0;
              LOWORD(v24) = 0;
              FormatRRASErrorString(
                &v28,
                L"UpdateRoutes: %ws returned %d while trying to update routes. Trying other protocols",
                *(_QWORD *)(i[3] + 32LL),
                v21);
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v22 = &v23;
                if ( v7 != -688 )
                  LODWORD(v22) = v7 + 688;
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasRtrmgrParamTraceInfo,
                  (unsigned int)&v28,
                  (_DWORD)v22,
                  *(_QWORD *)(v7 + 72),
                  (__int64)&v24);
              }
            }
          }
        }
        RtlReleaseResource(&stru_18008C4A0);
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"UpdateRoutes : No interface with ICB number %d", a1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
      }
      v12 = 1413;
    }
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: UpdateRoutes");
    goto LABEL_34;
  }
  LeaveCriticalSection(&RouterStateLock);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, L"error %d on RM API", 900);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
  }
  return 900;
}

```

## disassembly

```asm
0x18002bf1c  mov     [rsp+arg_8], rbx
0x18002bf21  mov     [rsp+arg_10], rsi
0x18002bf26  push    rdi
0x18002bf27  push    r12
0x18002bf29  push    r13
0x18002bf2b  push    r14
0x18002bf2d  push    r15
0x18002bf2f  sub     rsp, 880h
0x18002bf36  mov     rax, cs:__security_cookie
0x18002bf3d  xor     rax, rsp
0x18002bf40  mov     [rsp+8A8h+var_38], rax
0x18002bf48  mov     r14d, r8d
0x18002bf4b  mov     r13, rdx
0x18002bf4e  mov     rsi, rcx
0x18002bf51  xor     r12d, r12d
0x18002bf54  xor     edx, edx; Val
0x18002bf56  mov     [rsp+8A8h+var_838], r12d
0x18002bf5b  mov     r8d, 7FCh; Size
0x18002bf61  lea     rcx, [rsp+8A8h+var_834]; void *
0x18002bf66  call    memset_0
0x18002bf6b  xorps   xmm0, xmm0
0x18002bf6e  mov     [rsp+8A8h+var_860], r12d
0x18002bf73  xor     eax, eax
0x18002bf75  lea     rcx, RouterStateLock; lpCriticalSection
0x18002bf7c  movups  [rsp+8A8h+var_85C], xmm0
0x18002bf81  mov     [rsp+8A8h+var_83C], eax
0x18002bf85  movups  [rsp+8A8h+var_84C], xmm0
0x18002bf8a  movups  [rsp+8A8h+var_870], xmm0
0x18002bf8f  call    cs:__imp_EnterCriticalSection
0x18002bf95  cmp     dword ptr cs:RouterState, r12d
0x18002bf9c  lea     rcx, RouterStateLock; lpCriticalSection
0x18002bfa3  jnz     loc_18002C3EF
0x18002bfa9  inc     dword ptr cs:RouterState+4
0x18002bfaf  call    cs:__imp_LeaveCriticalSection
0x18002bfb5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002bfbc  lea     rdi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002bfc3  jge     short loc_18002C000
0x18002bfc5  lea     r8, aUpdateroutes; "UpdateRoutes"
0x18002bfcc  mov     word ptr [rsp+8A8h+var_838], r12w
0x18002bfd2  lea     rdx, aEnteredWs; "Entered: %ws"
0x18002bfd9  lea     rcx, [rsp+8A8h+var_838]
0x18002bfde  call    FormatRRASErrorString
0x18002bfe3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002bfea  jge     short loc_18002C000
0x18002bfec  lea     r8, [rsp+8A8h+var_838]
0x18002bff1  mov     rcx, rdi
0x18002bff4  lea     rdx, RasRtrmgrTraceInfo
0x18002bffb  call    McTemplateU0z_EventWriteTransfer
0x18002c000  mov     dl, 1; Wait
0x18002c002  lea     rcx, Resource; Resource
0x18002c009  call    cs:__imp_RtlAcquireResourceShared
0x18002c00f  mov     ecx, esi
0x18002c011  call    InterfaceLookupByICBSeqNumber
0x18002c016  mov     rbx, rax
0x18002c019  test    rax, rax
0x18002c01c  jz      loc_18002C375
0x18002c022  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18002c029  lea     rsi, RasRtrmgrParamTraceInfo
0x18002c030  test    cl, cl
0x18002c032  jns     short loc_18002C09D
0x18002c034  mov     word ptr [rsp+8A8h+var_838], r12w
0x18002c03a  lea     rdx, aUpdateroutesUp; "UpdateRoutes: Updating routes over %ws"
0x18002c041  mov     word ptr [rsp+8A8h+var_860], r12w
0x18002c047  lea     rcx, [rsp+8A8h+var_838]
0x18002c04c  mov     r8, [rax+48h]
0x18002c050  call    FormatRRASErrorString
0x18002c055  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18002c05c  test    cl, cl
0x18002c05e  jns     short loc_18002C09D
0x18002c060  lea     rax, [rbx+2B0h]
0x18002c067  mov     rdx, rsi
0x18002c06a  test    rax, rax
0x18002c06d  lea     r9, [rsp+8A8h+var_870]
0x18002c072  lea     r8, [rsp+8A8h+var_838]
0x18002c077  mov     rcx, rdi
0x18002c07a  cmovnz  r9, rax
0x18002c07e  lea     rax, [rsp+8A8h+var_860]
0x18002c083  mov     [rsp+8A8h+var_880], rax
0x18002c088  mov     rax, [rbx+48h]
0x18002c08c  mov     [rsp+8A8h+var_888], rax
0x18002c091  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c096  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18002c09d  cmp     dword ptr [rbx+0A8h], 4
0x18002c0a4  jnb     loc_18002C16C
0x18002c0aa  test    cl, cl
0x18002c0ac  jns     short loc_18002C10E
0x18002c0ae  mov     word ptr [rsp+8A8h+var_838], r12w
0x18002c0b4  lea     rdx, aUpdateroutesWs_0; "UpdateRoutes: %ws is not connected."
0x18002c0bb  mov     word ptr [rsp+8A8h+var_860], r12w
0x18002c0c1  lea     rcx, [rsp+8A8h+var_838]
0x18002c0c6  mov     r8, [rbx+48h]
0x18002c0ca  call    FormatRRASErrorString
0x18002c0cf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002c0d6  jge     short loc_18002C10E
0x18002c0d8  lea     rax, [rbx+2B0h]
0x18002c0df  mov     rdx, rsi
0x18002c0e2  test    rax, rax
0x18002c0e5  lea     r9, [rsp+8A8h+var_870]
0x18002c0ea  lea     r8, [rsp+8A8h+var_838]
0x18002c0ef  mov     rcx, rdi
0x18002c0f2  cmovnz  r9, rax
0x18002c0f6  lea     rax, [rsp+8A8h+var_860]
0x18002c0fb  mov     [rsp+8A8h+var_880], rax
0x18002c100  mov     rax, [rbx+48h]
0x18002c104  mov     [rsp+8A8h+var_888], rax
0x18002c109  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c10e  lea     rcx, Resource; Resource
0x18002c115  call    cs:__imp_RtlReleaseResource
0x18002c11b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002c122  jz      short loc_18002C162
0x18002c124  lea     rax, [rbx+2B0h]
0x18002c12b  mov     word ptr [rsp+8A8h+var_860], r12w
0x18002c131  test    rax, rax
0x18002c134  lea     r9, [rsp+8A8h+var_870]
0x18002c139  lea     r8, aLeavingUpdater; "Leaving: UpdateRoutes"
0x18002c140  mov     rdx, rsi
0x18002c143  cmovnz  r9, rax
0x18002c147  mov     rcx, rdi
0x18002c14a  lea     rax, [rsp+8A8h+var_860]
0x18002c14f  mov     [rsp+8A8h+var_880], rax
0x18002c154  mov     rax, [rbx+48h]
0x18002c158  mov     [rsp+8A8h+var_888], rax
0x18002c15d  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c162  mov     esi, 57h ; 'W'
0x18002c167  jmp     loc_18002C25D
0x18002c16c  mov     edx, 21h ; '!'
0x18002c171  lea     r15, [rbx+2B0h]
0x18002c178  cmp     r14d, edx
0x18002c17b  mov     r8d, 2712h; unsigned int
0x18002c181  mov     rcx, r15; struct _GUID *
0x18002c184  lea     esi, [rdx+36h]
0x18002c187  cmovnz  edx, esi; unsigned int
0x18002c18a  call    GetRtmRegistrationHandle
0x18002c18f  mov     edx, [rbx+10h]; CriteriaInterface
0x18002c192  xor     r8d, r8d
0x18002c195  mov     rcx, rax; RtmRegHandle
0x18002c198  call    DeleteRtmRoutes
0x18002c19d  mov     esi, eax
0x18002c19f  test    eax, eax
0x18002c1a1  jz      loc_18002C284
0x18002c1a7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002c1ae  jz      short loc_18002C20C
0x18002c1b0  mov     r8d, eax
0x18002c1b3  mov     word ptr [rsp+8A8h+var_838], r12w
0x18002c1b9  lea     rdx, aUpdateroutesEr; "UpdateRoutes: Error %d block deleting r"...
0x18002c1c0  mov     word ptr [rsp+8A8h+var_860], r12w
0x18002c1c6  lea     rcx, [rsp+8A8h+var_838]
0x18002c1cb  call    FormatRRASErrorString
0x18002c1d0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002c1d7  jz      short loc_18002C20C
0x18002c1d9  lea     rax, [rsp+8A8h+var_860]
0x18002c1de  test    r15, r15
0x18002c1e1  mov     [rsp+8A8h+var_880], rax
0x18002c1e6  lea     r9, [rsp+8A8h+var_870]
0x18002c1eb  mov     rax, [rbx+48h]
0x18002c1ef  lea     r8, [rsp+8A8h+var_838]
0x18002c1f4  cmovnz  r9, r15
0x18002c1f8  mov     [rsp+8A8h+var_888], rax
0x18002c1fd  lea     rdx, RasRtrMgrParamTraceError
0x18002c204  mov     rcx, rdi
0x18002c207  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c20c  lea     rcx, Resource; Resource
0x18002c213  call    cs:__imp_RtlReleaseResource
0x18002c219  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002c220  jz      short loc_18002C25D
0x18002c222  lea     rax, [rsp+8A8h+var_860]
0x18002c227  mov     word ptr [rsp+8A8h+var_860], r12w
0x18002c22d  mov     [rsp+8A8h+var_880], rax
0x18002c232  lea     r9, [rsp+8A8h+var_870]
0x18002c237  mov     rax, [rbx+48h]
0x18002c23b  lea     r8, aLeavingUpdater; "Leaving: UpdateRoutes"
0x18002c242  test    r15, r15
0x18002c245  mov     [rsp+8A8h+var_888], rax
0x18002c24a  lea     rdx, RasRtrmgrParamTraceInfo
0x18002c251  mov     rcx, rdi
0x18002c254  cmovnz  r9, r15
0x18002c258  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c25d  lea     rcx, RouterStateLock; lpCriticalSection
0x18002c264  call    cs:__imp_EnterCriticalSection
0x18002c26a  dec     dword ptr cs:RouterState+4
0x18002c270  lea     rcx, RouterStateLock; lpCriticalSection
0x18002c277  call    cs:__imp_LeaveCriticalSection
0x18002c27d  mov     eax, esi
0x18002c27f  jmp     loc_18002C440
0x18002c284  cmp     [rbx+0C0h], r12
0x18002c28b  jz      short loc_18002C297
0x18002c28d  mov     esi, 38Fh
0x18002c292  jmp     loc_18002C3BA
0x18002c297  mov     dl, 1; Wait
0x18002c299  lea     rcx, stru_18008C4A0; Resource
0x18002c2a0  mov     esi, 2
0x18002c2a5  call    cs:__imp_RtlAcquireResourceShared
0x18002c2ab  lea     r12, [rbx+38h]
0x18002c2af  mov     r14, [r12]
0x18002c2b3  cmp     r14, r12
0x18002c2b6  jz      loc_18002C366
0x18002c2bc  mov     rax, [r14+18h]
0x18002c2c0  mov     rax, [rax+0B0h]
0x18002c2c7  test    rax, rax
0x18002c2ca  jz      loc_18002C352
0x18002c2d0  mov     ecx, [rbx+10h]
0x18002c2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2d8  mov     esi, eax
0x18002c2da  test    eax, eax
0x18002c2dc  jz      short loc_18002C35A
0x18002c2de  cmp     eax, 258h
0x18002c2e3  jz      short loc_18002C35A
0x18002c2e5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002c2ec  jge     short loc_18002C352
0x18002c2ee  xor     ecx, ecx
0x18002c2f0  lea     rdx, aUpdateroutesWs; "UpdateRoutes: %ws returned %d while try"...
0x18002c2f7  mov     word ptr [rsp+8A8h+var_838], cx
0x18002c2fc  mov     r9d, eax
0x18002c2ff  mov     word ptr [rsp+8A8h+var_860], cx
0x18002c304  lea     rcx, [rsp+8A8h+var_838]
0x18002c309  mov     r8, [r14+18h]
0x18002c30d  mov     r8, [r8+20h]
0x18002c311  call    FormatRRASErrorString
0x18002c316  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18002c31d  jge     short loc_18002C352
0x18002c31f  lea     rax, [rsp+8A8h+var_860]
0x18002c324  test    r15, r15
0x18002c327  mov     [rsp+8A8h+var_880], rax
0x18002c32c  lea     r9, [rsp+8A8h+var_870]
0x18002c331  mov     rax, [rbx+48h]
0x18002c335  lea     r8, [rsp+8A8h+var_838]
0x18002c33a  cmovnz  r9, r15
0x18002c33e  mov     [rsp+8A8h+var_888], rax
0x18002c343  lea     rdx, RasRtrmgrParamTraceInfo
0x18002c34a  mov     rcx, rdi
0x18002c34d  call    McTemplateU0zjzz_EventWriteTransfer
0x18002c352  mov     r14, [r14]
0x18002c355  jmp     loc_18002C2B3
0x18002c35a  mov     esi, 258h
0x18002c35f  mov     [rbx+0C0h], r13
0x18002c366  lea     rcx, stru_18008C4A0; Resource
0x18002c36d  call    cs:__imp_RtlReleaseResource
0x18002c373  jmp     short loc_18002C3BA
0x18002c375  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002c37c  jge     short loc_18002C3B5
0x18002c37e  mov     r8d, esi
0x18002c381  mov     word ptr [rsp+8A8h+var_838], r12w
0x18002c387  lea     rdx, aUpdateroutesNo; "UpdateRoutes : No interface with ICB nu"...
0x18002c38e  lea     rcx, [rsp+8A8h+var_838]
0x18002c393  call    FormatRRASErrorString
0x18002c398  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002c39f  jge     short loc_18002C3B5
0x18002c3a1  lea     r8, [rsp+8A8h+var_838]
0x18002c3a6  mov     rcx, rdi
0x18002c3a9  lea     rdx, RasRtrmgrTraceInfo
0x18002c3b0  call    McTemplateU0z_EventWriteTransfer
0x18002c3b5  mov     esi, 585h
0x18002c3ba  lea     rcx, Resource; Resource
0x18002c3c1  call    cs:__imp_RtlReleaseResource
0x18002c3c7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18002c3ce  jz      loc_18002C25D
0x18002c3d4  lea     r8, aLeavingUpdater; "Leaving: UpdateRoutes"
0x18002c3db  mov     rcx, rdi
0x18002c3de  lea     rdx, RasRtrmgrTraceInfo
0x18002c3e5  call    McTemplateU0z_EventWriteTransfer
0x18002c3ea  jmp     loc_18002C25D
0x18002c3ef  call    cs:__imp_LeaveCriticalSection
0x18002c3f5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002c3fc  mov     ebx, 384h
0x18002c401  jge     short loc_18002C43E
0x18002c403  mov     r8d, ebx
0x18002c406  mov     word ptr [rsp+8A8h+var_838], r12w
0x18002c40c  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x18002c413  lea     rcx, [rsp+8A8h+var_838]
0x18002c418  call    FormatRRASErrorString
0x18002c41d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r12b
0x18002c424  jge     short loc_18002C43E
0x18002c426  lea     r8, [rsp+8A8h+var_838]
0x18002c42b  lea     rdx, RasRtrmgrTraceInfo
0x18002c432  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002c439  call    McTemplateU0z_EventWriteTransfer
0x18002c43e  mov     eax, ebx
0x18002c440  mov     rcx, [rsp+8A8h+var_38]
0x18002c448  xor     rcx, rsp; StackCookie
0x18002c44b  call    __security_check_cookie
0x18002c450  lea     r11, [rsp+8A8h+var_28]
0x18002c458  mov     rbx, [r11+38h]
0x18002c45c  mov     rsi, [r11+40h]
0x18002c460  mov     rsp, r11
0x18002c463  pop     r15
0x18002c465  pop     r14
0x18002c467  pop     r13
0x18002c469  pop     r12
0x18002c46b  pop     rdi
0x18002c46c  retn
```
