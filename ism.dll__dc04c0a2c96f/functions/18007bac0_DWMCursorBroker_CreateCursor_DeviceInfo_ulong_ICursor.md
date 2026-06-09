# DWMCursorBroker::CreateCursor(DeviceInfo *,ulong,ICursor * *)

- ea: `0x18007bac0`
- end: `0x18007be39`
- name: `?CreateCursor@DWMCursorBroker@@UEAAJPEAUDeviceInfo@@KPEAPEAUICursor@@@Z`
- size: `889`
- prototype: `__int64 __fastcall(DWMCursorBroker *__hidden this, struct DeviceInfo *, unsigned int, struct ICursor **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180012b74`
- `0x180012ee0`
- `0x180033c84`
- `0x1800651d8`
- `0x18007bac0`
- `0x18008dcac`
- `0x18008e404`
- `0x18008ead4`
- `0x1800f0990`
- `0x1801321e0`
- `0x1801ce010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18007bb39`
- `msvcp_win!_Mtx_unlock` at `0x18007be14`
- `msvcp_win!_Mtx_unlock` at `0x18007bb39`
- `msvcp_win!_Mtx_unlock` at `0x18007be14`

## string_xrefs

- `0x18007bb20`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18007bc25`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18007bcd2`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18007bd07`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18007bd3a`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`
- `0x18007bdb7`: `onecoreuap\windows\moderncore\inputv2\systeminputrouters\dwm\components\cursor\lib\dwmcursorbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DWMCursorBroker::CreateCursor(
        DWMCursorBroker *this,
        struct DeviceInfo *a2,
        int a3,
        struct ICursor **a4)
{
  int v8; // eax
  unsigned int v10; // r10d
  __int64 v11; // r8
  unsigned __int64 i; // rcx
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rax
  struct ICursor *v17; // r14
  int v18; // eax
  __int64 (__fastcall *v19)(DWMCursorBroker *, __int64 *); // rbx
  int v20; // eax
  _DWORD *v21; // rbx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  struct InputSystemServerConnection *BamoServerConnection; // rax
  __int64 v26; // rax
  int v27; // ebx
  int v28; // edi
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // [rsp+20h] [rbp-58h] BYREF
  struct ICursor *v33; // [rsp+28h] [rbp-50h] BYREF
  __int64 v34; // [rsp+30h] [rbp-48h] BYREF
  int v35; // [rsp+38h] [rbp-40h] BYREF
  void *v36; // [rsp+40h] [rbp-38h]
  _BYTE v37[16]; // [rsp+48h] [rbp-30h] BYREF
  __int128 v38; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v36 = &DWMCursorBroker::s_lock;
  std::_Mutex_base::lock((std::_Mutex_base *)&DWMCursorBroker::s_lock);
  *a4 = 0;
  v33 = 0;
  v8 = *((_DWORD *)a2 + 1);
  if ( (v8 & 8) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x211,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
      (const char *)0x80070057LL,
      v32);
    _Mtx_unlock((_Mtx_t)&DWMCursorBroker::s_lock);
    return 2147942487LL;
  }
  else
  {
    if ( (v8 & 2) != 0 )
    {
      v10 = 64;
      if ( (v8 & 0x40) != 0 )
      {
        v32 = 2;
      }
      else
      {
        v10 = 2;
        v32 = 1;
      }
    }
    else
    {
      v10 = *((_DWORD *)a2 + 1);
      LODWORD(v32) = *((_DWORD *)this + 114);
      *((_DWORD *)this + 114) = v32 + 1;
      HIDWORD(v32) = 0;
    }
    v11 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
    {
      v13 = 0x100000001B3LL;
      v11 = 0x100000001B3LL * (*((unsigned __int8 *)&v32 + i) ^ (unsigned __int64)v11);
    }
    v14 = 2 * (v11 & *((_QWORD *)this + 12));
    v15 = *((_QWORD *)this + 9);
    v16 = *(_QWORD *)(v15 + 8 * v14 + 8);
    if ( v16 == *((_QWORD *)this + 7) )
    {
LABEL_15:
      v16 = 0;
    }
    else
    {
      v13 = *(_QWORD *)(v15 + 8 * v14);
      while ( (_DWORD)v32 != *(_DWORD *)(v16 + 16) )
      {
        if ( v16 == v13 )
          goto LABEL_15;
        v16 = *(_QWORD *)(v16 + 8);
      }
    }
    if ( !v16 || v16 == *((_QWORD *)this + 7) )
    {
      v18 = DWMCursor::Create(this, v32, v10, &v33);
      if ( v18 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x231,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dwmcursorbroker.cpp",
          (const char *)(unsigned int)v18,
          v32);
      v34 = 0;
      v19 = *(__int64 (__fastcall **)(DWMCursorBroker *, __int64 *))(*(_QWORD *)this + 40LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      v20 = v19(this, &v34);
      v17 = v33;
      if ( v20 >= 0 )
      {
        v33 = 0;
        v38 = 0;
        v21 = (_DWORD *)(*(__int64 (__fastcall **)(struct ICursor *, int *))(*(_QWORD *)v17 + 48LL))(v17, &v35);
        if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v34 + 48LL))(v34, v37) == *v21 )
        {
          v33 = *(struct ICursor **)((char *)this + 460);
        }
        else
        {
          v23 = (*(__int64 (__fastcall **)(__int64, struct ICursor **, char *))(*(_QWORD *)v34 + 40LL))(
                  v34,
                  &v33,
                  (char *)&v33 + 4);
          if ( v23 < 0 )
            wil::details::in1diag3::FailFast_Hr(
              retaddr,
              (void *)0x241,
              (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\"
                            "dwmcursorbroker.cpp",
              (const char *)(unsigned int)v23,
              v32);
        }
        v22 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v34 + 104LL))(v34, &v38);
        if ( v22 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x243,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dw"
                          "mcursorbroker.cpp",
            (const char *)(unsigned int)v22,
            v32);
        v24 = (*(__int64 (__fastcall **)(struct ICursor *, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(
                v17,
                (unsigned int)v33,
                HIDWORD(v33));
        if ( v24 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x245,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dw"
                          "mcursorbroker.cpp",
            (const char *)(unsigned int)v24,
            v32);
        BamoServerConnection = ISMStatics::GetBamoServerConnection();
        v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)BamoServerConnection + 31) + 8LL) + 232LL))(*((_QWORD *)BamoServerConnection + 31) + 8LL);
        if ( v26 )
        {
          v35 = 2;
          v27 = (int)v33;
          v28 = HIDWORD(v33);
          v29 = *(_QWORD *)std::_Hash<std::_Umap_traits<enum InputType,tagPOINT,std::_Uhash_compare<enum InputType,std::hash<enum InputType>,std::equal_to<enum InputType>>,std::allocator<std::pair<enum InputType const,tagPOINT>>,0>>::_Try_emplace<enum InputType const &,>(
                             v26 + 96,
                             v37,
                             &v35);
          *(_DWORD *)(v29 + 20) = v27;
          *(_DWORD *)(v29 + 24) = v28;
        }
        v30 = (*(__int64 (__fastcall **)(struct ICursor *, __int128 *))(*(_QWORD *)v17 + 96LL))(v17, &v38);
        if ( v30 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x253,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\components\\cursor\\lib\\dw"
                          "mcursorbroker.cpp",
            (const char *)(unsigned int)v30,
            v32);
      }
      v31 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
    }
    else
    {
      v17 = *(struct ICursor **)(v16 + 24);
      (*(void (__fastcall **)(struct ICursor *, __int64, __int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, v32, v15, v13);
    }
    if ( *(_DWORD *)a2 )
    {
      LODWORD(v34) = *(_DWORD *)a2;
      HIDWORD(v34) = a3;
      std::unordered_map<DWMPointerMapping,CursorId,DWMMappingHash,std::equal_to<DWMPointerMapping>,std::allocator<std::pair<DWMPointerMapping const,CursorId>>>::_Insert_or_assign<DWMPointerMapping,CursorId &>(
        (char *)this + 112,
        &v38,
        &v34,
        &v32);
    }
    *a4 = v17;
    _Mtx_unlock((_Mtx_t)&DWMCursorBroker::s_lock);
    return 0;
  }
}

```

## disassembly

```asm
0x18007bac0  push    rbp
0x18007bac2  push    rbx
0x18007bac3  push    rsi
0x18007bac4  push    rdi
0x18007bac5  push    r12
0x18007bac7  push    r13
0x18007bac9  push    r14
0x18007bacb  push    r15
0x18007bacd  mov     rbp, rsp
0x18007bad0  sub     rsp, 78h
0x18007bad4  mov     rax, cs:__security_cookie
0x18007badb  xor     rax, rsp
0x18007bade  mov     [rbp+var_10], rax
0x18007bae2  mov     r15, r9
0x18007bae5  mov     r13d, r8d
0x18007bae8  mov     r12, rdx
0x18007baeb  mov     rsi, rcx
0x18007baee  lea     rbx, ?s_lock@DWMCursorBroker@@0Vrecursive_mutex@std@@A; std::recursive_mutex DWMCursorBroker::s_lock
0x18007baf5  mov     [rbp+var_38], rbx
0x18007baf9  mov     rcx, rbx; this
0x18007bafc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18007bb01  nop
0x18007bb02  xor     edi, edi
0x18007bb04  mov     [r15], rdi
0x18007bb07  mov     [rbp+var_50], rdi
0x18007bb0b  mov     eax, [r12+4]
0x18007bb10  test    al, 8
0x18007bb12  jz      short loc_18007BB46
0x18007bb14  mov     rcx, [rbp+40h]; this
0x18007bb18  mov     ebx, 80070057h
0x18007bb1d  mov     r9d, ebx; char *
0x18007bb20  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007bb27  mov     edx, 211h; void *
0x18007bb2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007bb31  nop
0x18007bb32  lea     rcx, ?s_lock@DWMCursorBroker@@0Vrecursive_mutex@std@@A; _Mtx_t
0x18007bb39  call    cs:__imp__Mtx_unlock
0x18007bb3f  mov     eax, ebx
0x18007bb41  jmp     loc_18007BE1C
0x18007bb46  mov     ecx, 2
0x18007bb4b  test    cl, al
0x18007bb4d  jz      short loc_18007BB6B
0x18007bb4f  lea     r10d, [rcx+3Eh]
0x18007bb53  test    r10b, al
0x18007bb56  jz      short loc_18007BB5E
0x18007bb58  mov     [rbp+var_58], rcx
0x18007bb5c  jmp     short loc_18007BB84
0x18007bb5e  mov     r10d, ecx
0x18007bb61  mov     [rbp+var_58], 1
0x18007bb69  jmp     short loc_18007BB84
0x18007bb6b  mov     r10d, eax
0x18007bb6e  mov     eax, [rsi+1C8h]
0x18007bb74  mov     dword ptr [rbp+var_58], eax
0x18007bb77  inc     eax
0x18007bb79  mov     [rsi+1C8h], eax
0x18007bb7f  xor     eax, eax
0x18007bb81  mov     dword ptr [rbp+var_58+4], eax
0x18007bb84  mov     rdx, [rbp+var_58]
0x18007bb88  mov     [rbp+var_58], rdx
0x18007bb8c  mov     r8, 0CBF29CE484222325h
0x18007bb96  mov     rcx, rdi
0x18007bb99  movzx   eax, byte ptr [rbp+rcx+var_58]
0x18007bb9e  xor     r8, rax
0x18007bba1  mov     r9, 100000001B3h
0x18007bbab  imul    r8, r9
0x18007bbaf  inc     rcx
0x18007bbb2  cmp     rcx, 4
0x18007bbb6  jb      short loc_18007BB99
0x18007bbb8  mov     rcx, [rsi+60h]
0x18007bbbc  and     rcx, r8
0x18007bbbf  add     rcx, rcx
0x18007bbc2  mov     r8, [rsi+48h]
0x18007bbc6  mov     rax, [r8+rcx*8+8]
0x18007bbcb  cmp     rax, [rsi+38h]
0x18007bbcf  jz      short loc_18007BBE5
0x18007bbd1  mov     r9, [r8+rcx*8]
0x18007bbd5  cmp     edx, [rax+10h]
0x18007bbd8  jz      short loc_18007BBE8
0x18007bbda  cmp     rax, r9
0x18007bbdd  jz      short loc_18007BBE5
0x18007bbdf  mov     rax, [rax+8]
0x18007bbe3  jmp     short loc_18007BBD5
0x18007bbe5  mov     rax, rdi
0x18007bbe8  test    rax, rax
0x18007bbeb  jz      short loc_18007BC0B
0x18007bbed  cmp     rax, [rsi+38h]
0x18007bbf1  jz      short loc_18007BC0B
0x18007bbf3  mov     r14, [rax+18h]
0x18007bbf7  mov     rax, [r14]
0x18007bbfa  mov     rcx, r14
0x18007bbfd  mov     rax, [rax+8]
0x18007bc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc06  jmp     loc_18007BDEA
0x18007bc0b  lea     r9, [rbp+var_50]
0x18007bc0f  mov     r8d, r10d
0x18007bc12  mov     rcx, rsi
0x18007bc15  call    ?Create@DWMCursor@@KAJPEAVDWMCursorBroker@@UCursorId@@W4InputType@@PEAPEAV1@@Z; DWMCursor::Create(DWMCursorBroker *,CursorId,InputType,DWMCursor * *)
0x18007bc1a  mov     rcx, [rbp+40h]; this
0x18007bc1e  test    eax, eax
0x18007bc20  jns     short loc_18007BC37
0x18007bc22  mov     r9d, eax; char *
0x18007bc25  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007bc2c  mov     edx, 231h; void *
0x18007bc31  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18007bc37  mov     [rbp+var_48], rdi
0x18007bc3b  mov     rax, [rsi]
0x18007bc3e  mov     rbx, [rax+28h]
0x18007bc42  lea     rcx, [rbp+var_48]
0x18007bc46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007bc4b  lea     rdx, [rbp+var_48]
0x18007bc4f  mov     rcx, rsi
0x18007bc52  mov     rax, rbx
0x18007bc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc5a  mov     r14, [rbp+var_50]
0x18007bc5e  test    eax, eax
0x18007bc60  js      loc_18007BDC9
0x18007bc66  mov     [rbp+var_50], rdi
0x18007bc6a  xorps   xmm0, xmm0
0x18007bc6d  movups  [rbp+var_20], xmm0
0x18007bc71  mov     rax, [r14]
0x18007bc74  lea     rdx, [rbp+var_40]
0x18007bc78  mov     rcx, r14
0x18007bc7b  mov     rax, [rax+30h]
0x18007bc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc84  mov     rbx, rax
0x18007bc87  mov     rcx, [rbp+var_48]
0x18007bc8b  mov     rdx, [rcx]
0x18007bc8e  mov     rax, [rdx+30h]
0x18007bc92  lea     rdx, [rbp+var_30]
0x18007bc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bc9b  mov     ecx, [rax]
0x18007bc9d  cmp     ecx, [rbx]
0x18007bc9f  jnz     short loc_18007BCE4
0x18007bca1  mov     eax, [rsi+1CCh]
0x18007bca7  mov     dword ptr [rbp+var_50], eax
0x18007bcaa  mov     eax, [rsi+1D0h]
0x18007bcb0  mov     dword ptr [rbp+var_50+4], eax
0x18007bcb3  mov     rcx, [rbp+var_48]
0x18007bcb7  mov     rax, [rcx]
0x18007bcba  lea     rdx, [rbp+var_20]
0x18007bcbe  mov     rax, [rax+68h]
0x18007bcc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bcc7  mov     rcx, [rbp+40h]; this
0x18007bccb  test    eax, eax
0x18007bccd  jns     short loc_18007BD19
0x18007bccf  mov     r9d, eax; char *
0x18007bcd2  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007bcd9  mov     edx, 243h; void *
0x18007bcde  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18007bce4  mov     rcx, [rbp+var_48]
0x18007bce8  mov     rax, [rcx]
0x18007bceb  lea     r8, [rbp+var_50+4]
0x18007bcef  lea     rdx, [rbp+var_50]
0x18007bcf3  mov     rax, [rax+28h]
0x18007bcf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bcfc  mov     rcx, [rbp+40h]; this
0x18007bd00  test    eax, eax
0x18007bd02  jns     short loc_18007BCB3
0x18007bd04  mov     r9d, eax; char *
0x18007bd07  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007bd0e  mov     edx, 241h; void *
0x18007bd13  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18007bd19  mov     rax, [r14]
0x18007bd1c  mov     r8d, dword ptr [rbp+var_50+4]
0x18007bd20  mov     edx, dword ptr [rbp+var_50]
0x18007bd23  mov     rcx, r14
0x18007bd26  mov     rax, [rax+18h]
0x18007bd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bd2f  mov     rcx, [rbp+40h]; this
0x18007bd33  test    eax, eax
0x18007bd35  jns     short loc_18007BD4C
0x18007bd37  mov     r9d, eax; char *
0x18007bd3a  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007bd41  mov     edx, 245h; void *
0x18007bd46  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18007bd4c  call    ?GetBamoServerConnection@ISMStatics@@SAPEAVInputSystemServerConnection@@XZ; ISMStatics::GetBamoServerConnection(void)
0x18007bd51  mov     rcx, [rax+0F8h]
0x18007bd58  add     rcx, 8
0x18007bd5c  mov     rax, [rcx]
0x18007bd5f  mov     rax, [rax+0E8h]
0x18007bd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bd6b  test    rax, rax
0x18007bd6e  jz      short loc_18007BD99
0x18007bd70  mov     [rbp+var_40], 2
0x18007bd77  mov     ebx, dword ptr [rbp+var_50]
0x18007bd7a  mov     edi, dword ptr [rbp+var_50+4]
0x18007bd7d  lea     rcx, [rax+60h]
0x18007bd81  lea     r8, [rbp+var_40]
0x18007bd85  lea     rdx, [rbp+var_30]
0x18007bd89  call    ??$_Try_emplace@AEBW4InputType@@$$V@?$_Hash@V?$_Umap_traits@W4InputType@@UtagPOINT@@V?$_Uhash_compare@W4InputType@@U?$hash@W4InputType@@@std@@U?$equal_to@W4InputType@@@3@@std@@V?$allocator@U?$pair@$$CBW4InputType@@UtagPOINT@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBW4InputType@@UtagPOINT@@@std@@PEAX@std@@_N@1@AEBW4InputType@@@Z; std::_Hash<std::_Umap_traits<InputType,tagPOINT,std::_Uhash_compare<InputType,std::hash<InputType>,std::equal_to<InputType>>,std::allocator<std::pair<InputType const,tagPOINT>>,0>>::_Try_emplace<InputType const &,>(InputType const &)
0x18007bd8e  mov     rcx, [rax]
0x18007bd91  mov     [rcx+14h], ebx
0x18007bd94  mov     [rcx+18h], edi
0x18007bd97  xor     edi, edi
0x18007bd99  mov     rax, [r14]
0x18007bd9c  lea     rdx, [rbp+var_20]
0x18007bda0  mov     rcx, r14
0x18007bda3  mov     rax, [rax+60h]
0x18007bda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bdac  mov     rcx, [rbp+40h]; this
0x18007bdb0  test    eax, eax
0x18007bdb2  jns     short loc_18007BDC9
0x18007bdb4  mov     r9d, eax; char *
0x18007bdb7  lea     r8, aOnecoreuapWind_73; "onecoreuap\\windows\\moderncore\\inputv"...
0x18007bdbe  mov     edx, 253h; void *
0x18007bdc3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18007bdc9  mov     rcx, [rbp+var_48]
0x18007bdcd  test    rcx, rcx
0x18007bdd0  jz      short loc_18007BDE3
0x18007bdd2  mov     [rbp+var_48], rdi
0x18007bdd6  mov     rax, [rcx]
0x18007bdd9  mov     rax, [rax+10h]
0x18007bddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bde2  nop
0x18007bde3  lea     rbx, ?s_lock@DWMCursorBroker@@0Vrecursive_mutex@std@@A; std::recursive_mutex DWMCursorBroker::s_lock
0x18007bdea  mov     eax, [r12]
0x18007bdee  test    eax, eax
0x18007bdf0  jz      short loc_18007BE0E
0x18007bdf2  mov     dword ptr [rbp+var_48], eax
0x18007bdf5  mov     dword ptr [rbp+var_48+4], r13d
0x18007bdf9  lea     rcx, [rsi+70h]
0x18007bdfd  lea     r9, [rbp+var_58]
0x18007be01  lea     r8, [rbp+var_48]
0x18007be05  lea     rdx, [rbp+var_20]
0x18007be09  call    ??$_Insert_or_assign@UDWMPointerMapping@@AEAUCursorId@@@?$unordered_map@UDWMPointerMapping@@UCursorId@@UDWMMappingHash@@U?$equal_to@UDWMPointerMapping@@@std@@V?$allocator@U?$pair@$$CBUDWMPointerMapping@@UCursorId@@@std@@@5@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUDWMPointerMapping@@UCursorId@@@std@@@std@@@std@@@std@@_N@1@$$QEAUDWMPointerMapping@@AEAUCursorId@@@Z; std::unordered_map<DWMPointerMapping,CursorId,DWMMappingHash,std::equal_to<DWMPointerMapping>,std::allocator<std::pair<DWMPointerMapping const,CursorId>>>::_Insert_or_assign<DWMPointerMapping,CursorId &>(DWMPointerMapping &&,CursorId &)
0x18007be0e  mov     [r15], r14
0x18007be11  mov     rcx, rbx; _Mtx_t
0x18007be14  call    cs:__imp__Mtx_unlock
0x18007be1a  xor     eax, eax
0x18007be1c  mov     rcx, [rbp+var_10]
0x18007be20  xor     rcx, rsp; StackCookie
0x18007be23  call    __security_check_cookie
0x18007be28  add     rsp, 78h
0x18007be2c  pop     r15
0x18007be2e  pop     r14
0x18007be30  pop     r13
0x18007be32  pop     r12
0x18007be34  pop     rdi
0x18007be35  pop     rsi
0x18007be36  pop     rbx
0x18007be37  pop     rbp
0x18007be38  retn
```
