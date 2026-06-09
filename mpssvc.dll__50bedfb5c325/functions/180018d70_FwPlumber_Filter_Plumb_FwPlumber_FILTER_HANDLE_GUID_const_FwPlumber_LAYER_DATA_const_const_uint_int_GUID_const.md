# FwPlumber::Filter::Plumb(FwPlumber::FILTER_HANDLE &,_GUID const &,FwPlumber::LAYER_DATA const * * const,uint,int,_GUID const *)

- ea: `0x180018d70`
- end: `0x1800192d7`
- name: `?Plumb@Filter@FwPlumber@@QEAAXAEAUFILTER_HANDLE@2@AEBU_GUID@@QEAPEBULAYER_DATA@2@IHPEBU4@@Z`
- size: `1383`
- prototype: `void __usercall(FWPM_FILTER0 *filter@<rcx>, struct FILTER_HANDLE *@<rdx>, const struct _GUID *@<r8>, const struct FwPlumber::LAYER_DATA **const@<r9>, unsigned int, int, const struct _GUID *)`
- caller_count: `17`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016190`
- `0x1800180f0`
- `0x180019310`
- `0x18001b3bc`
- `0x18001d274`
- `0x18001f64c`
- `0x1800204cc`
- `0x18002195c`
- `0x180021ce4`
- `0x1800221c0`
- `0x180022c08`
- `0x180022c90`
- `0x1800239f0`
- `0x1800452b8`
- `0x180068548`
- `0x1800697b0`
- `0x1800e5864`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x180018d70`
- `0x1800192e0`
- `0x180021b80`
- `0x180042680`
- `0x18006ecd4`
- `0x1800729c0`
- `0x180073488`
- `0x180076940`
- `0x180076d72`
- `0x180076d96`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180018eee`
- `ntdll!EtwEventWrite` at `0x180018f33`
- `ntdll!EtwEventWrite` at `0x180018eee`
- `ntdll!EtwEventWrite` at `0x180018f33`
- `fwbase!FwAlloc` at `0x18001927a`
- `fwbase!FwAlloc` at `0x18001927a`
- `fwbase!FwFree` at `0x180019211`
- `fwbase!FwFree` at `0x180019211`
- `fwpuclnt!FwpmFilterAdd0` at `0x180018f0c`
- `fwpuclnt!FwpmFilterAdd0` at `0x180018f0c`

## pseudocode

```c
void __fastcall FwPlumber::Filter::Plumb(
        FWPM_FILTER0 *filter,
        struct FILTER_HANDLE *a2,
        const struct _GUID *a3,
        const struct FwPlumber::LAYER_DATA **const a4,
        unsigned int a5,
        int a6,
        const struct _GUID *a7)
{
  __int64 v11; // rcx
  __int64 v12; // rbp
  GUID **v14; // rax
  const struct FwPlumber::LAYER_DATA **v15; // rbx
  UINT32 flags; // eax
  union FWPM_FILTER0_::$3EBD324B5084973F2C5A080A15E9AF59 *v17; // rbx
  UINT64 rawContext; // rcx
  DWORD v19; // eax
  __int64 v20; // rcx
  DWORD v21; // ebx
  _DWORD *v22; // rbx
  bool v23; // zf
  __int64 v24; // rdi
  union FWPM_FILTER0_::$3EBD324B5084973F2C5A080A15E9AF59 v25; // xmm0
  _DWORD *v26; // rax
  FwPlumber *v27; // rcx
  int v28; // r8d
  unsigned __int64 v29; // rcx
  GUID v30; // xmm0
  wchar_t *name; // r14
  char *v32; // rdi
  __int64 v33; // rbp
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rsi
  char *v37; // rax
  __int64 v38; // rbp
  unsigned int v39; // edx
  int pExceptionObject; // [rsp+20h] [rbp-58h] BYREF
  UINT64 id; // [rsp+28h] [rbp-50h] BYREF

  id = 0;
  v11 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_BYTE *)(v11 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v11 + 16), 12, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, 2147942487LL);
    pExceptionObject = -2147024809;
    throw (FwPlumber::Exception *)&pExceptionObject;
  }
  if ( !engineHandle )
  {
    if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_BYTE *)(v11 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v11 + 16), 12, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, 2147942406LL);
    pExceptionObject = -2147024890;
    throw (FwPlumber::Exception *)&pExceptionObject;
  }
  v12 = 0;
  for ( filter->subLayerKey = *a3; (unsigned int)v12 < a5; *(_QWORD *)&v22[2 * v24 + 4] = id )
  {
    v14 = (GUID **)a4[v12];
    v15 = &a4[v12];
    if ( !v14 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          12,
          WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids,
          2147942487LL);
      pExceptionObject = -2147024809;
      throw (FwPlumber::Exception *)&pExceptionObject;
    }
    v23 = (filter->action.type & 0x4000) == 0;
    filter->layerKey = **v14;
    if ( !v23 )
    {
      v29 = *(_QWORD *)&filter->action.filterType.Data1 - *(_QWORD *)&FW_PLUMBER_CALLOUT_KEY.Data1;
      if ( !v29 )
      {
        v29 = *((unsigned int *)&filter->action.bitmapIndex + 2)
            - (unsigned __int64)*(unsigned int *)FW_PLUMBER_CALLOUT_KEY.Data4;
        if ( !v29 )
          v29 = *((unsigned __int16 *)&filter->action.bitmapIndex + 6)
              - (unsigned __int64)*(unsigned __int16 *)&FW_PLUMBER_CALLOUT_KEY.Data4[4];
      }
      if ( !v29 )
      {
        if ( *((_WORD *)*v15 + 4) > 0xFFu )
          MicrosoftTelemetryAssertTriggeredNoArgs(0);
        filter->action.filterType.Data4[7] = *((_BYTE *)*v15 + 8);
      }
    }
    if ( a7 )
    {
      v30 = *a7++;
      filter->filterKey = v30;
    }
    flags = filter->flags;
    if ( (flags & 4) == 0 )
    {
      v17 = (union FWPM_FILTER0_::$3EBD324B5084973F2C5A080A15E9AF59 *)*((_QWORD *)a2 + 10);
      if ( v17 )
      {
        rawContext = v17->rawContext;
        if ( !v17->rawContext )
          rawContext = *(_QWORD *)v17->providerContextKey.Data4;
        if ( rawContext )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 83, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
            flags = filter->flags;
          }
          v25 = *v17;
          filter->flags = flags | 0x1004;
          filter->152 = v25;
        }
      }
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_BFE_FilterAdd_Enter, 0, 0);
    v19 = FwpmFilterAdd0(engineHandle, filter, 0, &id);
    v20 = g_Provider;
    v21 = v19;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_BFE_FilterAdd_Exit, 0, 0);
    if ( v21 == -2144206839 )
    {
      if ( !a6 )
      {
LABEL_64:
        name = filter->displayData.name;
        v32 = 0;
        v33 = (unsigned int)dword_180137DB4;
        if ( g_FwFilterError == 10 )
        {
          v34 = *((_QWORD *)&g_FwFilterError + 2 * (unsigned int)dword_180137DB4 + 2);
          if ( v34 )
            FwFree(v34);
          *(_OWORD *)((char *)&g_FwFilterError + 16 * (unsigned int)v33 + 8) = 0;
        }
        else
        {
          ++g_FwFilterError;
        }
        if ( name )
        {
          v35 = -1;
          do
            v23 = name[++v35] == 0;
          while ( !v23 );
          v36 = 2 * v35;
          v37 = (char *)FwAlloc(2 * v35 + 2);
          v32 = v37;
          if ( v37 )
          {
            memcpy_0(v37, name, v36 + 2);
            *(_WORD *)&v32[v36] = 0;
          }
        }
        v38 = 2 * v33;
        *((_DWORD *)&g_FwFilterError + 2 * v38 + 2) = v21;
        *((_QWORD *)&g_FwFilterError + v38 + 2) = v32;
        v39 = (dword_180137DB4 + 1) / 0xAu;
        dword_180137DB4 = (dword_180137DB4 + 1) % 0xAu;
        FwPlumber::ThrowWin32((FwPlumber *)v21, v39);
      }
    }
    else
    {
      if ( v21 )
        goto LABEL_64;
      v20 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_I(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, id);
    }
    v22 = (_DWORD *)*((_QWORD *)a2 + 11);
    if ( *(_QWORD *)v22 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20);
    v23 = *((_WORD *)v22 + 4) == 8;
    if ( *((__int16 *)v22 + 4) > 8 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v20);
      v23 = *((_WORD *)v22 + 4) == 8;
    }
    if ( v23 )
    {
      v26 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v26;
      if ( v26 )
      {
        *(_QWORD *)v26 = 0;
        v26[2] = 0;
        memset_0(v26 + 4, 0, 0x40u);
      }
      else
      {
        v22 = 0;
      }
      LOBYTE(v27) = v22 == 0;
      FwPlumber::ThrowIf(v27, 14, v28);
      **((_QWORD **)a2 + 11) = v22;
      *((_QWORD *)a2 + 11) = v22;
    }
    if ( *((__int16 *)v22 + 4) > 8 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20);
    v24 = *((__int16 *)v22 + 4);
    *((_WORD *)v22 + 4) = v24 + 1;
    if ( (__int16)v24 >= 8 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v20);
    ++qword_180137F30;
    v12 = (unsigned int)(v12 + 1);
  }
}

```

## disassembly

```asm
0x180018d70  push    rbx
0x180018d72  push    rsi
0x180018d73  push    rdi
0x180018d74  push    r13
0x180018d76  push    r14
0x180018d78  sub     rsp, 50h
0x180018d7c  mov     rax, cs:__security_cookie
0x180018d83  xor     rax, rsp
0x180018d86  mov     [rsp+78h+var_48], rax
0x180018d8b  mov     r14, r9
0x180018d8e  mov     [rsp+78h+id], 0
0x180018d97  mov     rbx, r8
0x180018d9a  mov     r13, rdx
0x180018d9d  mov     rsi, rcx
0x180018da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180018da7  lea     rdi, WPP_GLOBAL_Control
0x180018dae  cmp     rcx, rdi
0x180018db1  jz      short loc_180018DBD
0x180018db3  test    byte ptr [rcx+1Ch], 8
0x180018db7  jnz     loc_180019188
0x180018dbd  test    r14, r14
0x180018dc0  jnz     short loc_180018DE5
0x180018dc2  cmp     rcx, rdi
0x180018dc5  jnz     loc_180019095
0x180018dcb  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x180018dd2  mov     [rsp+78h+pExceptionObject], 80070057h
0x180018dda  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180018ddf  call    _CxxThrowException_0
0x180018de5  cmp     cs:engineHandle, 0
0x180018ded  jnz     short loc_180018E12
0x180018def  cmp     rcx, rdi
0x180018df2  jnz     loc_1800190BF
0x180018df8  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x180018dff  mov     [rsp+78h+pExceptionObject], 80070006h
0x180018e07  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180018e0c  call    _CxxThrowException_0
0x180018e12  movups  xmm0, xmmword ptr [rbx]
0x180018e15  mov     [rsp+78h+arg_10], rbp
0x180018e1d  xor     ebp, ebp
0x180018e1f  mov     [rsp+78h+var_38], r15
0x180018e24  mov     r15d, [rsp+78h+arg_20]
0x180018e2c  movups  xmmword ptr [rsi+50h], xmm0
0x180018e30  test    r15d, r15d
0x180018e33  jz      loc_180018FD1
0x180018e39  mov     [rsp+78h+var_30], r12
0x180018e3e  mov     r12, [rsp+78h+arg_30]
0x180018e46  mov     rax, [r14+rbp*8]
0x180018e4a  lea     rbx, [r14+rbp*8]
0x180018e4e  mov     edx, 0FFh
0x180018e53  test    rax, rax
0x180018e56  jnz     short loc_180018E82
0x180018e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e5f  cmp     rcx, rdi
0x180018e62  jnz     loc_1800190E9
0x180018e68  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x180018e6f  mov     [rsp+78h+pExceptionObject], 80070057h
0x180018e77  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180018e7c  call    _CxxThrowException_0
0x180018e82  test    dword ptr [rsi+80h], 4000h
0x180018e8c  mov     rax, [rax]
0x180018e8f  movups  xmm0, xmmword ptr [rax]
0x180018e92  movups  xmmword ptr [rsi+40h], xmm0
0x180018e96  jnz     loc_180019113
0x180018e9c  test    r12, r12
0x180018e9f  jnz     loc_1800191C5
0x180018ea5  mov     eax, [rsi+20h]
0x180018ea8  test    al, 4
0x180018eaa  jnz     short loc_180018ED5
0x180018eac  mov     rbx, [r13+50h]
0x180018eb0  test    rbx, rbx
0x180018eb3  jz      short loc_180018ED5
0x180018eb5  mov     rcx, [rbx]
0x180018eb8  sub     rcx, qword ptr cs:xmmword_1800FE0D0
0x180018ebf  jnz     short loc_180018ECC
0x180018ec1  mov     rcx, [rbx+8]
0x180018ec5  sub     rcx, qword ptr cs:xmmword_1800FE0D0+8
0x180018ecc  test    rcx, rcx
0x180018ecf  jnz     loc_180018FF8
0x180018ed5  mov     rcx, cs:g_Provider
0x180018edc  test    rcx, rcx
0x180018edf  jz      short loc_180018EFA
0x180018ee1  xor     r9d, r9d
0x180018ee4  lea     rdx, MPS_SVC_BFE_FilterAdd_Enter
0x180018eeb  xor     r8d, r8d
0x180018eee  call    cs:__imp_EtwEventWrite
0x180018ef5  nop     dword ptr [rax+rax+00h]
0x180018efa  mov     rcx, cs:engineHandle; engineHandle
0x180018f01  lea     r9, [rsp+78h+id]; id
0x180018f06  xor     r8d, r8d; sd
0x180018f09  mov     rdx, rsi; filter
0x180018f0c  call    cs:__imp_FwpmFilterAdd0
0x180018f13  nop     dword ptr [rax+rax+00h]
0x180018f18  mov     rcx, cs:g_Provider
0x180018f1f  mov     ebx, eax
0x180018f21  test    rcx, rcx
0x180018f24  jz      short loc_180018F3F
0x180018f26  xor     r9d, r9d
0x180018f29  lea     rdx, MPS_SVC_BFE_FilterAdd_Exit
0x180018f30  xor     r8d, r8d
0x180018f33  call    cs:__imp_EtwEventWrite
0x180018f3a  nop     dword ptr [rax+rax+00h]
0x180018f3f  cmp     ebx, 80320009h
0x180018f45  jz      loc_1800191D6
0x180018f4b  test    ebx, ebx
0x180018f4d  jnz     loc_1800191E4
0x180018f53  mov     rcx, cs:WPP_GLOBAL_Control
0x180018f5a  cmp     rcx, rdi
0x180018f5d  jz      short loc_180018F69
0x180018f5f  test    byte ptr [rcx+1Ch], 4
0x180018f63  jnz     loc_180019169
0x180018f69  mov     rbx, [r13+58h]
0x180018f6d  cmp     qword ptr [rbx], 0
0x180018f71  jnz     loc_180019228
0x180018f77  mov     edi, 8
0x180018f7c  cmp     di, [rbx+8]
0x180018f80  jl      loc_1800191B0
0x180018f86  jz      loc_18001903B
0x180018f8c  cmp     di, [rbx+8]
0x180018f90  jl      loc_180019232
0x180018f96  movsx   rdi, word ptr [rbx+8]
0x180018f9b  lea     eax, [rdi+1]
0x180018f9e  mov     [rbx+8], ax
0x180018fa2  mov     eax, 8
0x180018fa7  cmp     ax, di
0x180018faa  jle     loc_18001923C
0x180018fb0  inc     cs:qword_180137F30
0x180018fb7  inc     ebp
0x180018fb9  mov     rax, [rsp+78h+id]
0x180018fbe  mov     [rbx+rdi*8+10h], rax
0x180018fc3  cmp     ebp, r15d
0x180018fc6  jb      loc_180019246
0x180018fcc  mov     r12, [rsp+78h+var_30]
0x180018fd1  mov     rbp, [rsp+78h+arg_10]
0x180018fd9  mov     r15, [rsp+78h+var_38]
0x180018fde  mov     rcx, [rsp+78h+var_48]
0x180018fe3  xor     rcx, rsp; StackCookie
0x180018fe6  call    __security_check_cookie
0x180018feb  add     rsp, 50h
0x180018fef  pop     r14
0x180018ff1  pop     r13
0x180018ff3  pop     rdi
0x180018ff4  pop     rsi
0x180018ff5  pop     rbx
0x180018ff6  retn
0x180018ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fff  cmp     rcx, rdi
0x180019002  jnz     short loc_18001901B
0x180019004  movups  xmm0, xmmword ptr [rbx]
0x180019007  or      eax, 1004h
0x18001900c  mov     [rsi+20h], eax
0x18001900f  movups  xmmword ptr [rsi+98h], xmm0
0x180019016  jmp     loc_180018ED5
0x18001901b  test    byte ptr [rcx+1Ch], 8
0x18001901f  jz      short loc_180019004
0x180019021  mov     rcx, [rcx+10h]
0x180019025  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18001902c  mov     edx, 53h ; 'S'
0x180019031  call    WPP_SF_
0x180019036  mov     eax, [rsi+20h]
0x180019039  jmp     short loc_180019004
0x18001903b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019042  mov     ecx, 50h ; 'P'; unsigned __int64
0x180019047  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001904c  mov     rbx, rax
0x18001904f  test    rax, rax
0x180019052  jz      loc_1800191A9
0x180019058  xor     ecx, ecx
0x18001905a  mov     qword ptr [rax], 0
0x180019061  mov     [rax+8], ecx
0x180019064  xor     edx, edx; Val
0x180019066  lea     rcx, [rax+10h]; void *
0x18001906a  mov     r8d, 40h ; '@'; Size
0x180019070  call    memset_0
0x180019075  test    rbx, rbx
0x180019078  mov     edx, 0Eh; bool
0x18001907d  setz    cl; this
0x180019080  call    ?ThrowIf@FwPlumber@@YAX_NJ@Z; FwPlumber::ThrowIf(bool,long)
0x180019085  mov     rax, [r13+58h]
0x180019089  mov     [rax], rbx
0x18001908c  mov     [r13+58h], rbx
0x180019090  jmp     loc_180018F8C
0x180019095  test    byte ptr [rcx+1Ch], 1
0x180019099  jz      loc_180018DCB
0x18001909f  mov     rcx, [rcx+10h]
0x1800190a3  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x1800190aa  mov     edx, 0Ch
0x1800190af  mov     r9d, 80070057h
0x1800190b5  call    WPP_SF_d
0x1800190ba  jmp     loc_180018DCB
0x1800190bf  test    byte ptr [rcx+1Ch], 1
0x1800190c3  jz      loc_180018DF8
0x1800190c9  mov     rcx, [rcx+10h]
0x1800190cd  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x1800190d4  mov     edx, 0Ch
0x1800190d9  mov     r9d, 80070006h
0x1800190df  call    WPP_SF_d
0x1800190e4  jmp     loc_180018DF8
0x1800190e9  test    byte ptr [rcx+1Ch], 1
0x1800190ed  jz      loc_180018E68
0x1800190f3  mov     rcx, [rcx+10h]
0x1800190f7  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x1800190fe  mov     edx, 0Ch
0x180019103  mov     r9d, 80070057h
0x180019109  call    WPP_SF_d
0x18001910e  jmp     loc_180018E68
0x180019113  mov     rcx, [rsi+84h]
0x18001911a  sub     rcx, qword ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data1; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x180019121  jnz     short loc_180019145
0x180019123  mov     ecx, [rsi+8Ch]
0x180019129  mov     eax, dword ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data4; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x18001912f  sub     rcx, rax
0x180019132  jnz     short loc_180019145
0x180019134  movzx   ecx, word ptr [rsi+90h]
0x18001913b  movzx   eax, word ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data4+4; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x180019142  sub     rcx, rax
0x180019145  test    rcx, rcx
0x180019148  jnz     loc_180018E9C
0x18001914e  mov     rax, [rbx]
0x180019151  cmp     [rax+8], dx
0x180019155  ja      short loc_1800191BE
0x180019157  mov     rax, [rbx]
0x18001915a  movzx   ecx, byte ptr [rax+8]
0x18001915e  mov     [rsi+93h], cl
0x180019164  jmp     loc_180018E9C
0x180019169  mov     r9, [rsp+78h+id]
0x18001916e  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x180019175  mov     rcx, [rcx+10h]
0x180019179  mov     edx, 17h
0x18001917e  call    WPP_SF_I
0x180019183  jmp     loc_180018F69
0x180019188  mov     rcx, [rcx+10h]
0x18001918c  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x180019193  mov     edx, 16h
0x180019198  call    WPP_SF_
0x18001919d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800191a4  jmp     loc_180018DBD
0x1800191a9  xor     ebx, ebx
0x1800191ab  jmp     loc_180019075
0x1800191b0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "MAX_ID >= pData->NumIDs", "comparison before allocating last filter handle data")
0x1800191b5  cmp     di, [rbx+8]
0x1800191b9  jmp     loc_180018F86
0x1800191be  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Layers[i]->Id <= 0xff")
0x1800191c3  jmp     short loc_180019157
0x1800191c5  movaps  xmm0, xmmword ptr [r12]
0x1800191ca  add     r12, 10h
0x1800191ce  movups  xmmword ptr [rsi], xmm0
0x1800191d1  jmp     loc_180018EA5
0x1800191d6  cmp     [rsp+78h+arg_28], 0
0x1800191de  jnz     loc_180018F69
0x1800191e4  mov     eax, cs:?g_FwFilterError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST g_FwFilterError
0x1800191ea  lea     r12, ?g_FwFilterError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST g_FwFilterError
0x1800191f1  mov     r14, [rsi+10h]
0x1800191f5  xor     edi, edi
0x1800191f7  mov     ebp, cs:dword_180137DB4
0x1800191fd  cmp     eax, 0Ah
0x180019200  jnz     short loc_180019252
0x180019202  mov     esi, ebp
0x180019204  add     rsi, rsi
0x180019207  mov     rcx, [r12+rsi*8+10h]
0x18001920c  test    rcx, rcx
0x18001920f  jz      short loc_18001921D
0x180019211  call    cs:__imp_FwFree
0x180019218  nop     dword ptr [rax+rax+00h]
0x18001921d  xorps   xmm0, xmm0
0x180019220  movups  xmmword ptr [r12+rsi*8+8], xmm0
0x180019226  jmp     short loc_18001925A
0x180019228  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Last->Next == NULL")
0x18001922d  jmp     loc_180018F77
0x180019232  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "MAX_ID >= pData->NumIDs", "comparison after allocating last filter handle data")
0x180019237  jmp     loc_180018F96
0x18001923c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "MAX_ID > i")
0x180019241  jmp     loc_180018FB0
0x180019246  lea     rdi, WPP_GLOBAL_Control
0x18001924d  jmp     loc_180018E46
0x180019252  inc     eax
0x180019254  mov     cs:?g_FwFilterError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A, eax; _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST g_FwFilterError
0x18001925a  test    r14, r14
0x18001925d  jz      short loc_1800192A3
0x18001925f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019266  cmp     [r14+rax*2+2], di
0x18001926c  lea     rax, [rax+1]
0x180019270  jnz     short loc_180019266
0x180019272  lea     rsi, [rax+rax]
0x180019276  lea     rcx, [rsi+2]
0x18001927a  call    cs:__imp_FwAlloc
0x180019281  nop     dword ptr [rax+rax+00h]
0x180019286  mov     rdi, rax
0x180019289  test    rax, rax
0x18001928c  jz      short loc_1800192A3
0x18001928e  lea     r8, [rsi+2]; Size
0x180019292  mov     rdx, r14; Src
0x180019295  mov     rcx, rax; void *
0x180019298  call    memcpy_0
0x18001929d  xor     ecx, ecx
0x18001929f  mov     [rsi+rdi], cx
0x1800192a3  add     rbp, rbp
0x1800192a6  mov     eax, 0CCCCCCCDh
0x1800192ab  mov     [r12+rbp*8+8], ebx
0x1800192b0  mov     [r12+rbp*8+10h], rdi
0x1800192b5  mov     ecx, cs:dword_180137DB4
  ... truncated ...
```
