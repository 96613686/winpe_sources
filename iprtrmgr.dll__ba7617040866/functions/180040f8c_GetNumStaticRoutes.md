# GetNumStaticRoutes

- ea: `0x180040f8c`
- end: `0x180041265`
- name: `GetNumStaticRoutes`
- size: `729`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e94c`
- `0x180040e14`

## callees

- `0x180011790`
- `0x180040f8c`
- `0x180057aa4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800411e8`
- `KERNEL32!HeapFree` at `0x1800411e8`
- `KERNEL32!HeapAlloc` at `0x18004103a`
- `KERNEL32!HeapAlloc` at `0x18004103a`
- `rtm!RtmReleaseRoutes` at `0x1800411bd`
- `rtm!RtmReleaseRoutes` at `0x1800411bd`
- `rtm!RtmGetEnumRoutes` at `0x1800411a8`
- `rtm!RtmGetEnumRoutes` at `0x1800411a8`
- `rtm!RtmCreateRouteEnum` at `0x180041116`
- `rtm!RtmCreateRouteEnum` at `0x180041116`
- `rtm!RtmDeleteEnumHandle` at `0x1800411cf`
- `rtm!RtmDeleteEnumHandle` at `0x1800411cf`

## string_xrefs

- `0x1800411fe`: `GetNumStaticRoutes: Arithmatic Overflow during allocation of memory for handles\n`

## pseudocode

```c
__int64 __fastcall GetNumStaticRoutes(__int64 a1)
{
  unsigned __int64 v2; // rax
  int v3; // esi
  UINT v4; // ebx
  HANDLE *v5; // r14
  const wchar_t *v6; // r8
  __int64 *v7; // rdx
  unsigned int v8; // r12d
  unsigned int i; // esi
  void *v10; // r15
  DWORD v11; // eax
  __int64 v12; // r9
  __int128 *v13; // r9
  DWORD EnumRoutes; // ebx
  __int128 *v16; // r9
  unsigned int NumRoutes; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh]
  HANDLE EnumHandle; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v20[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD RtmRegHandle[11]; // [rsp+68h] [rbp-98h]
  __int128 v22; // [rsp+C0h] [rbp-40h] BYREF
  int v23; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v24; // [rsp+D4h] [rbp-2Ch]
  __int128 v25; // [rsp+E4h] [rbp-1Ch]
  int v26; // [rsp+F4h] [rbp-Ch]
  int v27; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v28[2044]; // [rsp+104h] [rbp+4h] BYREF

  EnumHandle = 0;
  NumRoutes = 0;
  memset_0(v20, 0, 0x60u);
  v27 = 0;
  memset_0(v28, 0, sizeof(v28));
  v23 = 0;
  v26 = 0;
  v2 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  v24 = 0;
  v25 = 0;
  v22 = 0;
  if ( v2 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v6 = L"GetNumStaticRoutes: Arithmatic Overflow during allocation of memory for handles\n";
      LOWORD(v23) = 0;
      v7 = RasRtrmgrParamTraceInfo;
      goto LABEL_21;
    }
    return 0;
  }
  v3 = *(_DWORD *)(a1 + 516);
  v18 = v3;
  v4 = 8 * g_rtmProfile.MaxHandlesInEnum;
  v5 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v2);
  if ( !v5 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v27) = 0;
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v27, L"GetNumStaticRoutes: Error allocating %d bytes for handles\n", v4);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v6 = (const wchar_t *)&v27;
        v7 = RasRtrMgrParamTraceError;
LABEL_21:
        v16 = &v22;
        if ( a1 != -688 )
          LODWORD(v16) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v7,
          (_DWORD)v6,
          (_DWORD)v16,
          *(_QWORD *)(a1 + 72),
          (__int64)&v23);
        return 0;
      }
    }
    return 0;
  }
  GetAllRtmRegistrationHandles(a1 + 688, v3 != 0 ? 33 : 87, v20);
  v8 = 0;
  for ( i = 0; i < 5; ++i )
  {
    if ( v20[4 * i + 1] )
    {
      v10 = (void *)RtmRegHandle[2 * i];
      v11 = RtmCreateRouteEnum(v10, 0, v18 != 0 ? 3 : 1, 0x10000u, 0, 0x10u, 0, *(_DWORD *)(a1 + 16), &EnumHandle);
      if ( v11 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v12 = (unsigned int)v20[4 * i];
          LOWORD(v27) = 0;
          LOWORD(v23) = 0;
          FormatRRASErrorString(&v27, L"GetNumStaticRoutes: Error %d creating handle for %d\n", v11, v12);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v13 = &v22;
            if ( a1 != -688 )
              LODWORD(v13) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v27,
              (_DWORD)v13,
              *(_QWORD *)(a1 + 72),
              (__int64)&v23);
          }
        }
      }
      else
      {
        do
        {
          NumRoutes = g_rtmProfile.MaxHandlesInEnum;
          EnumRoutes = RtmGetEnumRoutes(v10, EnumHandle, &NumRoutes, v5);
          v8 += NumRoutes;
          RtmReleaseRoutes(v10, NumRoutes, v5);
        }
        while ( !EnumRoutes );
        RtmDeleteEnumHandle(v10, EnumHandle);
      }
    }
  }
  HeapFree(IPRouterHeap, 0, v5);
  return v8;
}

```

## disassembly

```asm
0x180040f8c  push    rbp
0x180040f8e  push    rbx
0x180040f8f  push    rsi
0x180040f90  push    rdi
0x180040f91  push    r12
0x180040f93  push    r13
0x180040f95  push    r14
0x180040f97  push    r15
0x180040f99  lea     rbp, [rsp-818h]
0x180040fa1  sub     rsp, 918h
0x180040fa8  mov     rax, cs:__security_cookie
0x180040faf  xor     rax, rsp
0x180040fb2  mov     [rbp+850h+var_50], rax
0x180040fb9  xor     edx, edx; Val
0x180040fbb  mov     [rsp+950h+EnumHandle], 0
0x180040fc4  mov     rdi, rcx
0x180040fc7  mov     [rsp+950h+NumRoutes], 0
0x180040fcf  lea     rcx, [rsp+950h+var_8F0]; void *
0x180040fd4  lea     r8d, [rdx+60h]; Size
0x180040fd8  call    memset_0
0x180040fdd  xor     eax, eax
0x180040fdf  lea     rcx, [rbp+850h+var_84C]; void *
0x180040fe3  xor     edx, edx; Val
0x180040fe5  mov     [rbp+850h+var_850], eax
0x180040fe8  mov     r8d, 7FCh; Size
0x180040fee  call    memset_0
0x180040ff3  xor     eax, eax
0x180040ff5  xorps   xmm0, xmm0
0x180040ff8  mov     [rbp+850h+var_880], eax
0x180040ffb  mov     ecx, 0FFFFFFFFh
0x180041000  mov     [rbp+850h+var_85C], eax
0x180041003  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180041009  shl     rax, 3
0x18004100d  movups  [rbp+850h+var_87C], xmm0
0x180041011  movups  [rbp+850h+var_86C], xmm0
0x180041015  movups  [rbp+850h+var_890], xmm0
0x180041019  cmp     rax, rcx
0x18004101c  ja      loc_1800411F3
0x180041022  mov     esi, [rdi+204h]
0x180041028  xor     edx, edx; dwFlags
0x18004102a  mov     rcx, cs:IPRouterHeap; hHeap
0x180041031  mov     r8d, eax; dwBytes
0x180041034  mov     [rsp+950h+var_8FC], esi
0x180041038  mov     ebx, eax
0x18004103a  call    cs:__imp_HeapAlloc
0x180041040  mov     r14, rax
0x180041043  test    rax, rax
0x180041046  jnz     short loc_18004108D
0x180041048  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004104f  jz      loc_180041240
0x180041055  mov     r8d, ebx
0x180041058  mov     word ptr [rbp+850h+var_850], ax
0x18004105c  lea     rdx, aGetnumstaticro_1; "GetNumStaticRoutes: Error allocating %d"...
0x180041063  mov     word ptr [rbp+850h+var_880], ax
0x180041067  lea     rcx, [rbp+850h+var_850]
0x18004106b  call    FormatRRASErrorString
0x180041070  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180041077  jz      loc_180041240
0x18004107d  lea     r8, [rbp+850h+var_850]
0x180041081  lea     rdx, RasRtrMgrParamTraceError
0x180041088  jmp     loc_180041210
0x18004108d  mov     eax, esi
0x18004108f  lea     r13, [rdi+2B0h]
0x180041096  neg     eax
0x180041098  lea     r8, [rsp+950h+var_8F0]
0x18004109d  mov     rcx, r13
0x1800410a0  sbb     edx, edx
0x1800410a2  and     edx, 0FFFFFFCAh
0x1800410a5  add     edx, 57h ; 'W'
0x1800410a8  call    GetAllRtmRegistrationHandles
0x1800410ad  xor     r12d, r12d
0x1800410b0  xor     esi, esi
0x1800410b2  cmp     esi, 5
0x1800410b5  jnb     loc_1800411DC
0x1800410bb  mov     ebx, esi
0x1800410bd  add     rbx, rbx
0x1800410c0  cmp     [rsp+rbx*8+950h+var_8EC], 0
0x1800410c5  jz      loc_1800411D5
0x1800410cb  mov     eax, [rsp+950h+var_8FC]
0x1800410cf  mov     r9d, 10000h; EnumFlags
0x1800410d5  mov     r15, [rsp+rbx*8+950h+RtmRegHandle]
0x1800410da  neg     eax
0x1800410dc  lea     rax, [rsp+950h+EnumHandle]
0x1800410e1  mov     rcx, r15; RtmRegHandle
0x1800410e4  mov     [rsp+950h+RtmEnumHandle], rax; RtmEnumHandle
0x1800410e9  sbb     r8d, r8d
0x1800410ec  mov     eax, [rdi+10h]
0x1800410ef  and     r8d, 2
0x1800410f3  mov     [rsp+950h+CriteriaInterface], eax; CriteriaInterface
0x1800410f7  inc     r8d; TargetViews
0x1800410fa  mov     [rsp+950h+CriteriaRoute], 0; CriteriaRoute
0x180041103  xor     edx, edx; DestHandle
0x180041105  mov     [rsp+950h+MatchingFlags], 10h; MatchingFlags
0x18004110d  mov     [rsp+950h+StartDest], 0; StartDest
0x180041116  call    cs:__imp_RtmCreateRouteEnum
0x18004111c  test    eax, eax
0x18004111e  jz      short loc_18004118E
0x180041120  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180041127  jz      loc_1800411D5
0x18004112d  mov     r9d, [rsp+rbx*8+950h+var_8F0]
0x180041132  lea     rdx, aGetnumstaticro; "GetNumStaticRoutes: Error %d creating h"...
0x180041139  xor     ecx, ecx
0x18004113b  mov     r8d, eax
0x18004113e  mov     word ptr [rbp+850h+var_850], cx
0x180041142  mov     word ptr [rbp+850h+var_880], cx
0x180041146  lea     rcx, [rbp+850h+var_850]
0x18004114a  call    FormatRRASErrorString
0x18004114f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180041156  jz      short loc_1800411D5
0x180041158  lea     rax, [rbp+850h+var_880]
0x18004115c  test    r13, r13
0x18004115f  mov     qword ptr [rsp+950h+MatchingFlags], rax
0x180041164  lea     r9, [rbp+850h+var_890]
0x180041168  mov     rax, [rdi+48h]
0x18004116c  lea     r8, [rbp+850h+var_850]
0x180041170  cmovnz  r9, r13
0x180041174  mov     [rsp+950h+StartDest], rax
0x180041179  lea     rdx, RasRtrMgrParamTraceError
0x180041180  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041187  call    McTemplateU0zjzz_EventWriteTransfer
0x18004118c  jmp     short loc_1800411D5
0x18004118e  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x180041194  lea     r8, [rsp+950h+NumRoutes]; NumRoutes
0x180041199  mov     rdx, [rsp+950h+EnumHandle]; EnumHandle
0x18004119e  mov     r9, r14; RouteHandles
0x1800411a1  mov     rcx, r15; RtmRegHandle
0x1800411a4  mov     [rsp+950h+NumRoutes], eax
0x1800411a8  call    cs:__imp_RtmGetEnumRoutes
0x1800411ae  mov     edx, [rsp+950h+NumRoutes]; NumRoutes
0x1800411b2  mov     r8, r14; RouteHandles
0x1800411b5  mov     rcx, r15; RtmRegHandle
0x1800411b8  mov     ebx, eax
0x1800411ba  add     r12d, edx
0x1800411bd  call    cs:__imp_RtmReleaseRoutes
0x1800411c3  test    ebx, ebx
0x1800411c5  jz      short loc_18004118E
0x1800411c7  mov     rdx, [rsp+950h+EnumHandle]; EnumHandle
0x1800411cc  mov     rcx, r15; RtmRegHandle
0x1800411cf  call    cs:__imp_RtmDeleteEnumHandle
0x1800411d5  inc     esi
0x1800411d7  jmp     loc_1800410B2
0x1800411dc  mov     rcx, cs:IPRouterHeap; hHeap
0x1800411e3  mov     r8, r14; lpMem
0x1800411e6  xor     edx, edx; dwFlags
0x1800411e8  call    cs:__imp_HeapFree
0x1800411ee  mov     eax, r12d
0x1800411f1  jmp     short loc_180041242
0x1800411f3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800411fa  jz      short loc_180041240
0x1800411fc  xor     eax, eax
0x1800411fe  lea     r8, aGetnumstaticro_0; "GetNumStaticRoutes: Arithmatic Overflow"...
0x180041205  mov     word ptr [rbp+850h+var_880], ax
0x180041209  lea     rdx, RasRtrmgrParamTraceInfo
0x180041210  lea     rax, [rdi+2B0h]
0x180041217  test    rax, rax
0x18004121a  lea     r9, [rbp+850h+var_890]
0x18004121e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041225  cmovnz  r9, rax
0x180041229  lea     rax, [rbp+850h+var_880]
0x18004122d  mov     qword ptr [rsp+950h+MatchingFlags], rax
0x180041232  mov     rax, [rdi+48h]
0x180041236  mov     [rsp+950h+StartDest], rax
0x18004123b  call    McTemplateU0zjzz_EventWriteTransfer
0x180041240  xor     eax, eax
0x180041242  mov     rcx, [rbp+850h+var_50]
0x180041249  xor     rcx, rsp; StackCookie
0x18004124c  call    __security_check_cookie
0x180041251  add     rsp, 918h
0x180041258  pop     r15
0x18004125a  pop     r14
0x18004125c  pop     r13
0x18004125e  pop     r12
0x180041260  pop     rdi
0x180041261  pop     rsi
0x180041262  pop     rbx
0x180041263  pop     rbp
0x180041264  retn
```
