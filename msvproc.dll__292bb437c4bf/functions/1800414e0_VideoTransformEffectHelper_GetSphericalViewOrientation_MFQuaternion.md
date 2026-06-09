# VideoTransformEffectHelper::GetSphericalViewOrientation(MFQuaternion *)

- ea: `0x1800414e0`
- end: `0x180041776`
- name: `?GetSphericalViewOrientation@VideoTransformEffectHelper@@QEAAJPEAUMFQuaternion@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(VideoTransformEffectHelper *__hidden this, struct MFQuaternion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180053b00`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000ec20`
- `0x180025b08`
- `0x1800414e0`
- `0x180054140`
- `0x1800b64ec`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041740`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041586`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004161e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800416b2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041586`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004161e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800416b2`

## pseudocode

```c
__int64 __fastcall VideoTransformEffectHelper::GetSphericalViewOrientation(
        VideoTransformEffectHelper *this,
        struct MFQuaternion *a2)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v4)(__int64, __int64, __int64 *); // rbx
  int v5; // eax
  int v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v10; // r8d
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  int v15; // xmm0_4
  int v16; // xmm1_4
  int v17; // xmm2_4
  __int64 v19; // [rsp+20h] [rbp-50h] BYREF
  int v20; // [rsp+28h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v24; // [rsp+58h] [rbp-18h]

  v2 = *((_QWORD *)this + 2);
  v19 = 0;
  v22 = 0;
  v20 = 0;
  pv = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"sphericalViewOrientation", 0x19u, 0x18u);
  v5 = v4(v2, v24, &v19);
  v24 = 0;
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(&v19, &v22);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v22 + 264LL))(v22, &v20, &pv);
      if ( v6 >= 0 )
      {
        v15 = *(_DWORD *)pv;
        v16 = *((_DWORD *)pv + 1);
        v17 = *((_DWORD *)pv + 2);
        *(_DWORD *)a2 = *((_DWORD *)pv + 3);
        *((_DWORD *)a2 + 1) = v15;
        *((_DWORD *)a2 + 2) = v16;
        *((_DWORD *)a2 + 3) = v17;
      }
      else
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
          {
            v10 = 526;
            goto LABEL_10;
          }
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_180153440;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
        {
          v10 = 525;
          goto LABEL_10;
        }
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
      {
        v10 = 524;
LABEL_10:
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "VideoTransformEffectHelper::GetSphericalViewOrientation",
          v10,
          v6);
      }
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800414e0  mov     [rsp-18h+arg_10], rbx
0x1800414e5  push    rbp
0x1800414e6  push    rsi
0x1800414e7  push    rdi
0x1800414e8  mov     rbp, rsp
0x1800414eb  sub     rsp, 70h
0x1800414ef  mov     rax, cs:__security_cookie
0x1800414f6  xor     rax, rsp
0x1800414f9  mov     [rbp+var_10], rax
0x1800414fd  mov     rdi, [rcx+10h]
0x180041501  mov     rsi, rdx
0x180041504  mov     [rbp+var_50], 0
0x18004150c  lea     rcx, [rbp+var_50]
0x180041510  mov     [rbp+var_38], 0
0x180041518  mov     [rbp+var_48], 0
0x18004151f  mov     [rbp+pv], 0
0x180041527  mov     rax, [rdi]
0x18004152a  mov     rbx, [rax+30h]
0x18004152e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041533  mov     r9d, 18h; unsigned int
0x180041539  mov     [rbp+var_18], 0
0x180041541  lea     rdx, aSphericalviewo; "sphericalViewOrientation"
0x180041548  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004154c  lea     r8d, [r9+1]; unsigned int
0x180041550  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041555  mov     rdx, [rbp+var_18]
0x180041559  lea     r8, [rbp+var_50]
0x18004155d  mov     rcx, rdi
0x180041560  mov     rax, rbx
0x180041563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041568  mov     [rbp+var_18], 0
0x180041570  mov     ebx, eax
0x180041572  test    eax, eax
0x180041574  jns     loc_1800415FF
0x18004157a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041581  test    rcx, rcx
0x180041584  jnz     short loc_1800415C7
0x180041586  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004158c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041593  mov     rcx, rax
0x180041596  test    rax, rax
0x180041599  jz      short loc_1800415B9
0x18004159b  mov     rax, [rax]
0x18004159e  mov     edx, 7F0h
0x1800415a3  mov     rax, [rax+8]
0x1800415a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415ac  test    eax, eax
0x1800415ae  jz      short loc_1800415B9
0x1800415b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415b7  jmp     short loc_1800415C7
0x1800415b9  lea     rcx, qword_180153440; this
0x1800415c0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800415c7  cmp     byte ptr [rcx+8], 0
0x1800415cb  jz      loc_180041737
0x1800415d1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800415d6  cmp     [rax+7CCh], ebx
0x1800415dc  jz      loc_180041737
0x1800415e2  mov     r8d, 20Ch; int
0x1800415e8  mov     r9d, ebx; int
0x1800415eb  lea     rdx, aVideotransform_2; "VideoTransformEffectHelper::GetSpherica"...
0x1800415f2  mov     rcx, rax; this
0x1800415f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800415fa  jmp     loc_180041737
0x1800415ff  lea     rdx, [rbp+var_38]
0x180041603  lea     rcx, [rbp+var_50]
0x180041607  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x18004160c  mov     ebx, eax
0x18004160e  test    eax, eax
0x180041610  jns     short loc_180041685
0x180041612  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041619  test    rcx, rcx
0x18004161c  jnz     short loc_18004165F
0x18004161e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041624  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004162b  mov     rcx, rax
0x18004162e  test    rax, rax
0x180041631  jz      short loc_180041651
0x180041633  mov     rax, [rax]
0x180041636  mov     edx, 7F0h
0x18004163b  mov     rax, [rax+8]
0x18004163f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041644  test    eax, eax
0x180041646  jz      short loc_180041651
0x180041648  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004164f  jmp     short loc_18004165F
0x180041651  lea     rcx, qword_180153440; this
0x180041658  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004165f  cmp     byte ptr [rcx+8], 0
0x180041663  jz      loc_180041737
0x180041669  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004166e  cmp     [rax+7CCh], ebx
0x180041674  jz      loc_180041737
0x18004167a  mov     r8d, 20Dh
0x180041680  jmp     loc_1800415E8
0x180041685  mov     rcx, [rbp+var_38]
0x180041689  lea     r8, [rbp+pv]
0x18004168d  lea     rdx, [rbp+var_48]
0x180041691  mov     rax, [rcx]
0x180041694  mov     rax, [rax+108h]
0x18004169b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416a0  mov     ebx, eax
0x1800416a2  test    eax, eax
0x1800416a4  jns     short loc_180041711
0x1800416a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416ad  test    rcx, rcx
0x1800416b0  jnz     short loc_1800416F3
0x1800416b2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800416b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416bf  mov     rcx, rax
0x1800416c2  test    rax, rax
0x1800416c5  jz      short loc_1800416E5
0x1800416c7  mov     rax, [rax]
0x1800416ca  mov     edx, 7F0h
0x1800416cf  mov     rax, [rax+8]
0x1800416d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416d8  test    eax, eax
0x1800416da  jz      short loc_1800416E5
0x1800416dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416e3  jmp     short loc_1800416F3
0x1800416e5  lea     rcx, qword_180153440; this
0x1800416ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416f3  cmp     byte ptr [rcx+8], 0
0x1800416f7  jz      short loc_180041737
0x1800416f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800416fe  cmp     [rax+7CCh], ebx
0x180041704  jz      short loc_180041737
0x180041706  mov     r8d, 20Eh
0x18004170c  jmp     loc_1800415E8
0x180041711  mov     rax, [rbp+pv]
0x180041715  movss   xmm0, dword ptr [rax]
0x180041719  movss   xmm1, dword ptr [rax+4]
0x18004171e  movss   xmm2, dword ptr [rax+8]
0x180041723  mov     eax, [rax+0Ch]
0x180041726  mov     [rsi], eax
0x180041728  movss   dword ptr [rsi+4], xmm0
0x18004172d  movss   dword ptr [rsi+8], xmm1
0x180041732  movss   dword ptr [rsi+0Ch], xmm2
0x180041737  mov     rcx, [rbp+pv]; pv
0x18004173b  test    rcx, rcx
0x18004173e  jz      short loc_180041746
0x180041740  call    cs:__imp_CoTaskMemFree
0x180041746  lea     rcx, [rbp+var_38]
0x18004174a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004174f  lea     rcx, [rbp+var_50]
0x180041753  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041758  mov     eax, ebx
0x18004175a  mov     rcx, [rbp+var_10]
0x18004175e  xor     rcx, rsp; StackCookie
0x180041761  call    __security_check_cookie
0x180041766  mov     rbx, [rsp+70h+arg_10]
0x18004176e  add     rsp, 70h
0x180041772  pop     rdi
0x180041773  pop     rsi
0x180041774  pop     rbp
0x180041775  retn
```
