# Windows::UI::Composition::VisualCommon::Api::put_Offset(Windows::Foundation::Numerics::Vector3)

- ea: `0x180014580`
- end: `0x180014ae4`
- name: `?put_Offset@Api@VisualCommon@Composition@UI@Windows@@UEAAJUVector3@Numerics@Foundation@5@@Z`
- size: `1380`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007484`
- `0x180012da0`
- `0x180012ee8`
- `0x180013528`
- `0x18001358c`
- `0x180014580`
- `0x180014e14`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x1800171b0`
- `0x1800311c8`
- `0x18004a0b8`
- `0x18008c56c`
- `0x18008c610`
- `0x1800a0f58`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014741`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014741`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800145cb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800145cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800149d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800149ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800149ac`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014868`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014868`
- `ntdll!RtlLookupElementGenericTable` at `0x1800146aa`
- `ntdll!RtlLookupElementGenericTable` at `0x1800146aa`

## string_xrefs

- `0x18001485d`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180014a80`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCommon::Api::put_Offset(__int64 a1, float *a2)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  int v5; // ecx
  char v6; // r12
  __int64 v7; // rax
  int v8; // edi
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  Windows::UI::Composition::AnimationBindingManager **v10; // rax
  Windows::UI::Composition::AnimationBindingManager **v11; // r13
  char v12; // al
  unsigned int v13; // r14d
  int v14; // edx
  int v15; // ecx
  _QWORD *v16; // rcx
  __int128 v17; // rdi
  __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  void *v20; // rcx
  Windows::UI::Composition::AnimationBindingManager *v22; // rcx
  Windows::UI::Composition::AnimationBindingManager *i; // r14
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // r12d
  __int64 v27; // rax
  DirectComposition::CDevice *v28; // rdi
  _DWORD *v29; // rax
  Windows::UI::Composition::AnimationBindingManager *v30; // rdi
  Windows::UI::Composition::AnimationBindingManager *v31; // r12
  Windows::UI::Composition::AnimationBindingManager **v32; // r14
  Windows::UI::Composition::AnimationBindingManager *v33; // rax
  const WCHAR *v34; // r14
  unsigned __int64 v35; // rdi
  unsigned int v36; // eax
  UINT32 v37; // edx
  HRESULT v38; // eax
  __int64 v39; // rax
  int v40; // eax
  int v41; // [rsp+20h] [rbp-E0h] BYREF
  void *v42; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v43; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER Buffer; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v48[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h]
  int v50; // [rsp+B8h] [rbp-48h]
  int v51; // [rsp+F0h] [rbp-10h]
  char v52; // [rsp+F4h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v2 = a1 - 184;
  v3 = *(_QWORD *)(a1 - 184 + 24);
  if ( *(_DWORD *)(v3 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v3 + 56) + 24LL));
  v5 = *(_DWORD *)(v3 + 64);
  if ( v5 != *(_DWORD *)(v3 + 72) + *(_DWORD *)(v3 + 68) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v3 + 64) = v5 + 1;
  if ( (*(_BYTE *)(v2 + 48) & 2) != 0 )
  {
    if ( *(float *)(v2 + 256) == *a2 && *(float *)(v2 + 260) == a2[1] && *(float *)(v2 + 264) == a2[2] )
    {
      v6 = 0;
    }
    else
    {
      v6 = 1;
      *(_QWORD *)(v2 + 256) = *(_QWORD *)a2;
      *(float *)(v2 + 264) = a2[2];
    }
    v7 = *(_QWORD *)v2;
    BYTE2(v41) = v6;
    LOBYTE(v41) = 0;
    if ( !(*(__int64 (__fastcall **)(__int64))(v7 + 232))(v2) )
      goto LABEL_9;
    v34 = Windows::UI::Composition::VisualCommon::sc_Offset;
    v35 = -1;
    string = 0;
    do
      ++v35;
    while ( Windows::UI::Composition::VisualCommon::sc_Offset[v35] );
    if ( v35 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v36 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v35);
    v37 = v36 - 1;
    if ( (unsigned int)v35 < v36 )
      v37 = v35;
    v38 = WindowsCreateStringReference(v34, v37, &Buffer, &string);
    if ( v38 < 0 )
    {
      RaiseException(v38, 1u, 0, 0);
      __debugbreak();
    }
    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const struct Microsoft::WRL::Wrappers::HStringReference *)&Buffer);
    Windows::UI::Composition::AnimationValueData::AnimationValueData(v48, v39);
    v52 = v6;
    v51 = 52;
    v49 = *(_QWORD *)a2;
    v50 = *((_DWORD *)a2 + 2);
    v40 = (*(__int64 (__fastcall **)(__int64, _BYTE *, int *))(*(_QWORD *)v2 + 224LL))(v2, v48, &v41);
    v13 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
        (const char *)(unsigned int)v40,
        v41);
      DoStackCaptureDirect(v13, 0x9BFu);
    }
    else
    {
LABEL_9:
      if ( !(_BYTE)v41 )
      {
        v8 = dword_1801D8008 & 0x7FFFFFFF;
        BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager(*(Windows::UI::Composition::CompositorCommon **)(v2 + 24));
        LODWORD(v42) = *(_DWORD *)(v2 + 144);
        HIDWORD(v42) = v8;
        Buffer.Reserved.Reserved1 = v42;
        *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
        v10 = (Windows::UI::Composition::AnimationBindingManager **)RtlLookupElementGenericTable(
                                                                      BindingManager,
                                                                      &Buffer);
        v11 = v10;
        if ( v10 )
        {
          v22 = v10[1];
          BYTE1(v41) = 1;
          if ( v22 )
          {
            BYTE1(v41) = 1;
            do
            {
              *((_WORD *)v22 + 8) = 0;
              *((_BYTE *)v22 + 18) = 0;
              v22 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v22 + 3);
            }
            while ( v22 );
          }
          for ( i = v10[2]; i; i = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)i + 3) )
          {
            v25 = *((_QWORD *)i + 1);
            *((_WORD *)i + 8) = 0;
            *((_BYTE *)i + 18) = 0;
            v26 = *(_DWORD *)(v25 + 144);
            if ( v26 )
            {
              v27 = *(_QWORD *)(v25 + 24);
              v42 = 0;
              v28 = *(DirectComposition::CDevice **)(v27 + 440);
              DirectComposition::CDevice::BeginKernelCommand(v28, 0x18u, &v42, 0);
              v29 = v42;
              *(_DWORD *)v42 = 11;
              v29[1] = v26;
              v29[2] = 7;
              *((_QWORD *)v29 + 2) = 0;
              v22 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v28 + 11);
              if ( v22 )
                (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v22 + 24LL))(v22);
            }
          }
          v30 = v11[1];
          v31 = v30;
          while ( v30 )
          {
            v32 = (Windows::UI::Composition::AnimationBindingManager **)((char *)v30 + 24);
            if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
                   v22,
                   *(struct SubchannelMaskInfo **)v30) )
            {
              Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(*((_QWORD *)v30 + 1), 6, 1);
              v33 = *v32;
              if ( v30 == v11[1] )
                v11[1] = v33;
              else
                *((_QWORD *)v31 + 3) = v33;
              v22 = v30;
              v30 = *v32;
              *v32 = v11[2];
              v11[2] = v22;
            }
            else
            {
              v31 = v30;
              v30 = *v32;
            }
          }
          v12 = BYTE1(v41);
        }
        else
        {
          v12 = 0;
        }
        if ( BYTE2(v41) || v12 )
        {
          v24 = (unsigned int)dword_1801D8008;
          LODWORD(v24) = dword_1801D8008 & 0x7FFFFFFF;
          if ( byte_1801D8010 )
          {
            if ( byte_1801D8010 != 1 )
              Microsoft::WRL2::FailFast::Unexpected(0);
            Windows::UI::Composition::ProxyObject::SetBufferProperty(v2, v24, a2, 0xCu);
          }
          else
          {
            Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(v2, v24);
          }
        }
      }
      v13 = 0;
    }
    v14 = *(_DWORD *)(v3 + 72);
    v15 = v14 + *(_DWORD *)(v3 + 68);
    if ( --*(_DWORD *)(v3 + 64) != v15 )
      Microsoft::WRL2::FailFast::Unexpected("ContextSession end counts");
    v44 = 0;
    v43 = 0;
    if ( v14 || (v16 = (_QWORD *)(v3 + 120), &v43 == (__int128 *)(v3 + 120)) )
    {
      v17 = v43;
    }
    else
    {
      *(_QWORD *)&v17 = *v16;
      *v16 = 0;
      *((_QWORD *)&v17 + 1) = *(_QWORD *)(v3 + 128);
      *(_QWORD *)(v3 + 128) = 0;
      v44 = *(_QWORD *)(v3 + 136);
      v43 = v17;
      *(_QWORD *)(v3 + 136) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v3 + 56) + 24LL));
    if ( (_QWORD)v17 != *((_QWORD *)&v17 + 1) )
    {
      Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v43);
      v17 = v43;
      if ( (_QWORD)v43 != *((_QWORD *)&v43 + 1) )
      {
        std::_Destroy_range<std::allocator<std::function<void (void)>>>(v43, *((_QWORD *)&v43 + 1));
        *((_QWORD *)&v17 + 1) = v17;
      }
    }
    v18 = v17;
    if ( (_QWORD)v17 )
    {
      while ( v18 != *((_QWORD *)&v17 + 1) )
      {
        std::_Func_class<void,>::_Tidy(v18);
        v18 += 64;
      }
      v19 = (v44 - v17) & 0xFFFFFFFFFFFFFFC0uLL;
      if ( v19 >= 0x1000 )
      {
        v20 = *(void **)(v17 - 8);
        if ( (unsigned __int64)(v17 - (_QWORD)v20 - 8) > 0x1F )
          __fastfail(5u);
        v19 += 39LL;
      }
      else
      {
        v20 = (void *)v17;
      }
      operator delete(v20, v19);
    }
    return v13;
  }
  else
  {
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v3);
    return 2147483667LL;
  }
}

```

## disassembly

```asm
0x180014580  push    rbp
0x180014582  push    rbx
0x180014583  push    rsi
0x180014584  push    rdi
0x180014585  push    r12
0x180014587  push    r13
0x180014589  push    r14
0x18001458b  push    r15
0x18001458d  lea     rbp, [rsp-18h]
0x180014592  sub     rsp, 118h
0x180014599  mov     rax, cs:__security_cookie
0x1800145a0  xor     rax, rsp
0x1800145a3  mov     [rbp+50h+var_50], rax
0x1800145a7  lea     rsi, [rcx-0B8h]
0x1800145ae  xor     r13d, r13d
0x1800145b1  mov     rbx, [rsi+18h]
0x1800145b5  mov     r15, rdx
0x1800145b8  mov     eax, [rbx+5Ch]
0x1800145bb  test    eax, eax
0x1800145bd  jnz     loc_180014AA9
0x1800145c3  mov     rcx, [rbx+38h]
0x1800145c7  add     rcx, 18h; lpCriticalSection
0x1800145cb  call    cs:__imp_EnterCriticalSection
0x1800145d1  mov     eax, [rbx+44h]
0x1800145d4  add     eax, [rbx+48h]
0x1800145d7  mov     ecx, [rbx+40h]
0x1800145da  cmp     ecx, eax
0x1800145dc  jnz     loc_180014A0F
0x1800145e2  lea     eax, [rcx+1]
0x1800145e5  mov     [rbx+40h], eax
0x1800145e8  test    byte ptr [rsi+30h], 2
0x1800145ec  jz      loc_180014858
0x1800145f2  movss   xmm0, dword ptr [rsi+100h]
0x1800145fa  ucomiss xmm0, dword ptr [r15]
0x1800145fe  jp      loc_180014800
0x180014604  jnz     loc_180014800
0x18001460a  movss   xmm0, dword ptr [rsi+104h]
0x180014612  ucomiss xmm0, dword ptr [r15+4]
0x180014617  jp      loc_180014800
0x18001461d  jnz     loc_180014800
0x180014623  movss   xmm0, dword ptr [rsi+108h]
0x18001462b  ucomiss xmm0, dword ptr [r15+8]
0x180014630  jp      loc_180014800
0x180014636  jnz     loc_180014800
0x18001463c  mov     r12b, r13b
0x18001463f  mov     rax, [rsi]
0x180014642  mov     rcx, rsi
0x180014645  mov     byte ptr [rsp+150h+var_130+2], r12b
0x18001464a  mov     byte ptr [rsp+150h+var_130], r13b; int
0x18001464f  mov     rax, [rax+0E8h]
0x180014656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001465b  xor     r8d, r8d; nNumberOfArguments
0x18001465e  test    rax, rax
0x180014661  jnz     loc_18001496E
0x180014667  cmp     byte ptr [rsp+150h+var_130], r8b
0x18001466c  jnz     short loc_1800146D5
0x18001466e  mov     edi, cs:dword_1801D8008
0x180014674  mov     rcx, [rsi+18h]; this
0x180014678  btr     edi, 1Fh
0x18001467c  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x180014681  mov     ecx, [rsi+90h]
0x180014687  lea     rdx, [rsp+150h+Buffer]; Buffer
0x18001468c  mov     dword ptr [rsp+150h+var_128], ecx
0x180014690  xorps   xmm0, xmm0
0x180014693  mov     dword ptr [rsp+150h+var_128+4], edi
0x180014697  mov     rcx, [rsp+150h+var_128]
0x18001469c  mov     [rsp+150h+Buffer], rcx
0x1800146a1  mov     rcx, rax; Table
0x1800146a4  movdqu  [rsp+150h+var_E0], xmm0
0x1800146aa  call    cs:__imp_RtlLookupElementGenericTable
0x1800146b0  xor     r8d, r8d
0x1800146b3  mov     r13, rax
0x1800146b6  test    rax, rax
0x1800146b9  jnz     loc_1800147D2
0x1800146bf  mov     al, r8b
0x1800146c2  cmp     byte ptr [rsp+150h+var_130+2], r8b
0x1800146c7  jnz     loc_18001481F
0x1800146cd  test    al, al
0x1800146cf  jnz     loc_18001481F
0x1800146d5  mov     r14d, r8d
0x1800146d8  mov     ecx, [rbx+44h]
0x1800146db  mov     edx, [rbx+48h]
0x1800146de  add     ecx, edx
0x1800146e0  dec     dword ptr [rbx+40h]
0x1800146e3  cmp     [rbx+40h], ecx
0x1800146e6  jnz     loc_180014AD0
0x1800146ec  mov     [rsp+150h+var_110], r8
0x1800146f1  xorps   xmm0, xmm0
0x1800146f4  movdqu  [rsp+150h+var_120], xmm0
0x1800146fa  test    edx, edx
0x1800146fc  jnz     loc_18001495F
0x180014702  lea     rcx, [rbx+78h]
0x180014706  lea     rax, [rsp+150h+var_120]
0x18001470b  cmp     rax, rcx
0x18001470e  jz      loc_18001495F
0x180014714  mov     rdi, [rcx]
0x180014717  mov     [rcx], r8
0x18001471a  mov     rsi, [rcx+8]
0x18001471e  mov     [rcx+8], r8
0x180014722  mov     rax, [rcx+10h]
0x180014726  mov     [rsp+150h+var_110], rax
0x18001472b  mov     qword ptr [rsp+150h+var_120], rdi
0x180014730  mov     qword ptr [rsp+150h+var_120+8], rsi
0x180014735  mov     [rcx+10h], r8
0x180014739  mov     rcx, [rbx+38h]
0x18001473d  add     rcx, 18h; lpCriticalSection
0x180014741  call    cs:__imp_LeaveCriticalSection
0x180014747  cmp     rdi, rsi
0x18001474a  jz      short loc_180014773
0x18001474c  lea     rcx, [rsp+150h+var_120]
0x180014751  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x180014756  mov     rdi, qword ptr [rsp+150h+var_120]
0x18001475b  mov     rsi, qword ptr [rsp+150h+var_120+8]
0x180014760  cmp     rdi, rsi
0x180014763  jz      short loc_180014773
0x180014765  mov     rdx, rsi
0x180014768  mov     rcx, rdi
0x18001476b  call    ??$_Destroy_range@V?$allocator@V?$function@$$A6AXXZ@std@@@std@@@std@@YAXPEAV?$function@$$A6AXXZ@0@QEAV10@AEAV?$allocator@V?$function@$$A6AXXZ@std@@@0@@Z; std::_Destroy_range<std::allocator<std::function<void (void)>>>(std::function<void (void)> *,std::function<void (void)> * const,std::allocator<std::function<void (void)>> &)
0x180014770  mov     rsi, rdi
0x180014773  mov     rbx, rdi
0x180014776  test    rbx, rbx
0x180014779  jz      short loc_1800147AF
0x18001477b  jmp     short loc_180014789
0x18001477d  mov     rcx, rbx
0x180014780  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180014785  add     rbx, 40h ; '@'
0x180014789  cmp     rbx, rsi
0x18001478c  jnz     short loc_18001477D
0x18001478e  mov     rdx, [rsp+150h+var_110]
0x180014793  sub     rdx, rdi
0x180014796  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x18001479a  cmp     rdx, 1000h
0x1800147a1  jnb     loc_1800149DC
0x1800147a7  mov     rcx, rdi; void *
0x1800147aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800147af  mov     eax, r14d
0x1800147b2  mov     rcx, [rbp+50h+var_50]
0x1800147b6  xor     rcx, rsp; StackCookie
0x1800147b9  call    __security_check_cookie
0x1800147be  add     rsp, 118h
0x1800147c5  pop     r15
0x1800147c7  pop     r14
0x1800147c9  pop     r13
0x1800147cb  pop     r12
0x1800147cd  pop     rdi
0x1800147ce  pop     rsi
0x1800147cf  pop     rbx
0x1800147d0  pop     rbp
0x1800147d1  retn
0x1800147d2  mov     rcx, [rax+8]
0x1800147d6  mov     byte ptr [rsp+150h+var_130+1], 1
0x1800147db  test    rcx, rcx
0x1800147de  jz      short loc_1800147F7
0x1800147e0  mov     byte ptr [rsp+150h+var_130+1], 1
0x1800147e5  mov     [rcx+10h], r8w
0x1800147ea  mov     [rcx+12h], r8b
0x1800147ee  mov     rcx, [rcx+18h]
0x1800147f2  test    rcx, rcx
0x1800147f5  jnz     short loc_1800147E5
0x1800147f7  mov     r14, [rax+10h]
0x1800147fb  jmp     loc_180014890
0x180014800  movsd   xmm0, qword ptr [r15]
0x180014805  mov     r12b, 1
0x180014808  movsd   qword ptr [rsi+100h], xmm0
0x180014810  mov     eax, [r15+8]
0x180014814  mov     [rsi+108h], eax
0x18001481a  jmp     loc_18001463F
0x18001481f  mov     edx, cs:dword_1801D8008
0x180014825  mov     al, cs:byte_1801D8010
0x18001482b  btr     edx, 1Fh
0x18001482f  test    al, al
0x180014831  jz      loc_180014AB6
0x180014837  cmp     al, 1
0x180014839  jnz     loc_180014AC8
0x18001483f  mov     r9d, 0Ch
0x180014845  mov     r8, r15
0x180014848  mov     rcx, rsi
0x18001484b  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x180014850  xor     r8d, r8d
0x180014853  jmp     loc_1800146D5
0x180014858  mov     edi, 80000013h
0x18001485d  lea     r8, aTheGivenObject; "The given object has already been close"...
0x180014864  mov     ecx, edi
0x180014866  xor     edx, edx
0x180014868  call    cs:__imp_RoOriginateErrorW
0x18001486e  mov     rcx, rbx; this
0x180014871  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x180014876  mov     eax, edi
0x180014878  jmp     loc_1800147B2
0x18001487d  mov     rax, [rcx]
0x180014880  mov     rax, [rax+18h]
0x180014884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014889  xor     r8d, r8d
0x18001488c  mov     r14, [r14+18h]
0x180014890  test    r14, r14
0x180014893  jz      short loc_1800148FA
0x180014895  mov     rax, [r14+8]
0x180014899  mov     [r14+10h], r8w
0x18001489e  mov     [r14+12h], r8b
0x1800148a2  mov     r12d, [rax+90h]
0x1800148a9  test    r12d, r12d
0x1800148ac  jz      short loc_18001488C
0x1800148ae  mov     rax, [rax+18h]
0x1800148b2  xor     r9d, r9d; bool
0x1800148b5  mov     [rsp+150h+var_128], r8
0x1800148ba  lea     r8, [rsp+150h+var_128]; void **
0x1800148bf  mov     rdi, [rax+1B8h]
0x1800148c6  lea     edx, [r9+18h]; unsigned int
0x1800148ca  mov     rcx, rdi; this
0x1800148cd  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x1800148d2  mov     rax, [rsp+150h+var_128]
0x1800148d7  xor     r8d, r8d
0x1800148da  mov     dword ptr [rax], 0Bh
0x1800148e0  mov     [rax+4], r12d
0x1800148e4  mov     dword ptr [rax+8], 7
0x1800148eb  mov     [rax+10h], r8
0x1800148ef  mov     rcx, [rdi+58h]
0x1800148f3  test    rcx, rcx
0x1800148f6  jz      short loc_18001488C
0x1800148f8  jmp     short loc_18001487D
0x1800148fa  mov     rdi, [r13+8]
0x1800148fe  mov     r12, rdi
0x180014901  test    rdi, rdi
0x180014904  jnz     short loc_18001490F
0x180014906  mov     al, byte ptr [rsp+150h+var_130+1]
0x18001490a  jmp     loc_1800146C2
0x18001490f  mov     rdx, [rdi]; struct SubchannelMaskInfo *
0x180014912  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x180014917  xor     r8d, r8d
0x18001491a  lea     r14, [rdi+18h]
0x18001491e  test    ax, ax
0x180014921  jz      loc_1800149FA
0x180014927  mov     rcx, [rdi+8]
0x18001492b  lea     edx, [r8+6]
0x18001492f  lea     r8d, [rdx-5]
0x180014933  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x180014938  mov     rax, [r14]
0x18001493b  cmp     rdi, [r13+8]
0x18001493f  jnz     loc_180014A05
0x180014945  mov     [r13+8], rax
0x180014949  mov     rax, [r13+10h]
0x18001494d  mov     rcx, rdi
0x180014950  mov     rdi, [r14]
0x180014953  xor     r8d, r8d
0x180014956  mov     [r14], rax
0x180014959  mov     [r13+10h], rcx
0x18001495d  jmp     short loc_180014901
0x18001495f  mov     rsi, qword ptr [rsp+150h+var_120+8]
0x180014964  mov     rdi, qword ptr [rsp+150h+var_120]
0x180014969  jmp     loc_180014739
0x18001496e  mov     r14, cs:?sc_Offset@VisualCommon@Composition@UI@Windows@@0UAnimatedProperty@AnimationHelper@234@B; Windows::UI::Composition::AnimationHelper::AnimatedProperty const Windows::UI::Composition::VisualCommon::sc_Offset
0x180014975  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180014979  mov     [rbp+50h+string], r8
0x18001497d  inc     rdi
0x180014980  cmp     [r14+rdi*2], r8w
0x180014985  jnz     short loc_18001497D
0x180014987  mov     eax, 0FFFFFFFFh
0x18001498c  cmp     rdi, rax
0x18001498f  ja      short loc_1800149C9
0x180014991  mov     ecx, edi; unsigned int
0x180014993  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180014998  cmp     edi, eax
0x18001499a  lea     r9, [rbp+50h+string]; string
0x18001499e  lea     r8, [rsp+150h+Buffer]; hstringHeader
0x1800149a3  mov     rcx, r14; sourceString
0x1800149a6  lea     edx, [rax-1]
0x1800149a9  cmovb   edx, edi; length
0x1800149ac  call    cs:__imp_WindowsCreateStringReference
0x1800149b2  test    eax, eax
0x1800149b4  jns     short loc_180014A1C
0x1800149b6  xor     r9d, r9d; lpArguments
0x1800149b9  xor     r8d, r8d; nNumberOfArguments
0x1800149bc  mov     ecx, eax; dwExceptionCode
0x1800149be  lea     edx, [r9+1]; dwExceptionFlags
0x1800149c2  call    cs:__imp_RaiseException
0x1800149c8  int     3; Trap to Debugger
0x1800149c9  xor     r9d, r9d; lpArguments
0x1800149cc  mov     ecx, 80070216h; dwExceptionCode
0x1800149d1  lea     edx, [r9+1]; dwExceptionFlags
0x1800149d5  call    cs:__imp_RaiseException
0x1800149db  int     3; Trap to Debugger
0x1800149dc  mov     rcx, [rdi-8]
0x1800149e0  sub     rdi, rcx
0x1800149e3  sub     rdi, 8
0x1800149e7  cmp     rdi, 1Fh
0x1800149eb  ja      loc_180014ADD
0x1800149f1  add     rdx, 27h ; '''
0x1800149f5  jmp     loc_1800147AA
0x1800149fa  mov     r12, rdi
0x1800149fd  mov     rdi, [r14]
0x180014a00  jmp     loc_180014901
0x180014a05  mov     [r12+18h], rax
0x180014a0a  jmp     loc_180014949
0x180014a0f  lea     rcx, aContextsession; "ContextSession begin counts"
0x180014a16  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x180014a1c  lea     rdx, [rsp+150h+Buffer]; struct Microsoft::WRL::Wrappers::HStringReference *
0x180014a21  lea     rcx, [rsp+150h+hstringHeader]; hstringHeader
0x180014a26  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Microsoft::WRL::Wrappers::HStringReference const &)
0x180014a2b  mov     rdx, rax
0x180014a2e  lea     rcx, [rbp+50h+var_C0]
  ... truncated ...
```
