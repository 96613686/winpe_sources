# CWapDPUHelper::ExecV2Node(IConfigManager2 *,ushort const *,ConfigDataType,tagVARIANT,IResultTracker *)

- ea: `0x180026c80`
- end: `0x180026f3e`
- name: `?ExecV2Node@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGW4ConfigDataType@@UtagVARIANT@@PEAUIResultTracker@@@Z`
- size: `702`
- prototype: `int __high(struct IConfigManager2 *, const unsigned __int16 *, enum ConfigDataType, struct tagVARIANT, struct IResultTracker *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001488`
- `0x1800110bc`
- `0x180024308`
- `0x180026c80`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026dd7`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026dd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWapDPUHelper::ExecV2Node(
        __int64 a1,
        __int64 a2,
        const OLECHAR *a3,
        unsigned int a4,
        __int128 *a5,
        __int64 a6)
{
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // r9
  __int128 *v12; // r14
  wchar_t *v13; // rax
  __int64 v14; // rdx
  struct IUnknown *v16; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v17; // [rsp+48h] [rbp-41h] BYREF
  int v18; // [rsp+4Ch] [rbp-3Dh] BYREF
  __int64 v19; // [rsp+50h] [rbp-39h] BYREF
  int v20; // [rsp+58h] [rbp-31h] BYREF
  struct IUnknown *v21; // [rsp+60h] [rbp-29h] BYREF
  const OLECHAR *v22; // [rsp+68h] [rbp-21h] BYREF
  const OLECHAR *v23; // [rsp+70h] [rbp-19h] BYREF
  __int128 v24; // [rsp+80h] [rbp-9h] BYREF
  __int64 v25; // [rsp+90h] [rbp+7h]
  unsigned int v26; // [rsp+E8h] [rbp+5Fh] BYREF

  v16 = 0;
  v19 = 0;
  v21 = 0;
  v17 = 0;
  v26 = 0;
  v18 = 0;
  if ( !a2 || !a3 || (v9 = a6) == 0 )
  {
    v8 = -2147024809;
    goto LABEL_25;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, struct IUnknown **))(*(_QWORD *)a2 + 80LL))(a2, a3, &v16);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, int *))v16->lpVtbl[9].AddRef)(v16, &v18);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147023728 )
    {
      if ( (unsigned int)dword_18003E080 > 5 )
      {
        v22 = L"ExecV2Node";
        v23 = a3;
        v20 = v18;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          0x80000000LL,
          (unsigned __int8 *)&byte_1800377C7,
          v10,
          v11,
          (__int64)&v20,
          &v23,
          &v22);
      }
      v12 = a5;
      if ( v18 )
        goto LABEL_21;
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v16->lpVtbl[8].AddRef)(v16, &v19);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 144LL))(v19, &v17);
        if ( v8 >= 0 )
        {
          v13 = wcsrchr(a3, 0x2Fu);
          v14 = v13 ? (__int64)(v13 + 1) : (__int64)a3;
          v24 = *v12;
          v25 = *((_QWORD *)v12 + 2);
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, struct IUnknown **))(*(_QWORD *)v19 + 24LL))(
                 v19,
                 v14,
                 a4,
                 &v24,
                 &v21);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 144LL))(v19, &v26);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 48LL))(
                     v9,
                     v19,
                     v17,
                     v26);
              if ( v8 >= 0 )
              {
                if ( v16 != v21 )
                  ATL::AtlComPtrAssign(&v16, v21);
LABEL_21:
                v8 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))v16->lpVtbl[6].QueryInterface)(
                       v16,
                       &v17);
                if ( v8 >= 0 )
                {
                  v24 = *v12;
                  v25 = *((_QWORD *)v12 + 2);
                  v8 = ((__int64 (__fastcall *)(struct IUnknown *, __int128 *))v16->lpVtbl[3].Release)(v16, &v24);
                  if ( v8 >= 0 )
                  {
                    v8 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))v16->lpVtbl[6].QueryInterface)(
                           v16,
                           &v26);
                    if ( v8 >= 0 )
                      v8 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, _QWORD, _QWORD))(*(_QWORD *)v9 + 48LL))(
                             v9,
                             v16,
                             v17,
                             v26);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_25:
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v21);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v19);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180026c80  push    rbp
0x180026c82  push    rbx
0x180026c83  push    rsi
0x180026c84  push    rdi
0x180026c85  push    r14
0x180026c87  push    r15
0x180026c89  lea     rbp, [rsp-1Fh]
0x180026c8e  sub     rsp, 0A8h
0x180026c95  mov     r15d, r9d
0x180026c98  mov     rdi, r8
0x180026c9b  mov     r10, rdx
0x180026c9e  mov     [rbp+47h+var_90], 0
0x180026ca6  mov     [rbp+47h+var_80], 0
0x180026cae  mov     [rbp+47h+var_70], 0
0x180026cb6  mov     [rbp+47h+var_88], 0
0x180026cbd  mov     [rbp+47h+arg_8], 0
0x180026cc4  mov     [rbp+47h+var_84], 0
0x180026ccb  test    rdx, rdx
0x180026cce  jnz     short loc_180026CDA
0x180026cd0  mov     ebx, 80070057h
0x180026cd5  jmp     loc_180026F0E
0x180026cda  test    rdi, rdi
0x180026cdd  jz      short loc_180026CD0
0x180026cdf  mov     rsi, [rbp+47h+arg_28]
0x180026ce3  test    rsi, rsi
0x180026ce6  jz      short loc_180026CD0
0x180026ce8  mov     rax, [rdx]
0x180026ceb  lea     r8, [rbp+47h+var_90]
0x180026cef  mov     rdx, rdi
0x180026cf2  mov     rcx, r10
0x180026cf5  mov     rax, [rax+50h]
0x180026cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cfe  mov     ebx, eax
0x180026d00  test    eax, eax
0x180026d02  js      loc_180026F0E
0x180026d08  mov     rcx, [rbp+47h+var_90]
0x180026d0c  mov     rax, [rcx]
0x180026d0f  lea     rdx, [rbp+47h+var_84]
0x180026d13  mov     rax, [rax+0E0h]
0x180026d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d1f  mov     ebx, eax
0x180026d21  mov     ecx, 80000000h
0x180026d26  add     eax, ecx
0x180026d28  test    ecx, eax
0x180026d2a  jnz     short loc_180026D38
0x180026d2c  cmp     ebx, 80070490h
0x180026d32  jnz     loc_180026F0E
0x180026d38  mov     eax, cs:dword_18003E080
0x180026d3e  cmp     eax, 5
0x180026d41  jbe     short loc_180026D7F
0x180026d43  lea     rax, aExecv2node; "ExecV2Node"
0x180026d4a  mov     [rbp+47h+var_68], rax
0x180026d4e  mov     [rbp+47h+var_60], rdi
0x180026d52  mov     eax, [rbp+47h+var_84]
0x180026d55  mov     [rbp+47h+var_78], eax
0x180026d58  lea     rax, [rbp+47h+var_68]
0x180026d5c  mov     [rsp+0D0h+var_A0], rax
0x180026d61  lea     rax, [rbp+47h+var_60]
0x180026d65  mov     [rsp+0D0h+var_A8], rax
0x180026d6a  lea     rax, [rbp+47h+var_78]
0x180026d6e  mov     [rsp+0D0h+var_B0], rax
0x180026d73  lea     rdx, byte_1800377C7
0x180026d7a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180026d7f  mov     r14, [rbp+47h+arg_20]
0x180026d83  cmp     [rbp+47h+var_84], 0
0x180026d87  jnz     loc_180026E8A
0x180026d8d  mov     rcx, [rbp+47h+var_90]
0x180026d91  mov     rax, [rcx]
0x180026d94  lea     rdx, [rbp+47h+var_80]
0x180026d98  mov     rax, [rax+0C8h]
0x180026d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026da4  mov     ebx, eax
0x180026da6  test    eax, eax
0x180026da8  js      loc_180026F0E
0x180026dae  mov     rcx, [rbp+47h+var_80]
0x180026db2  mov     rax, [rcx]
0x180026db5  lea     rdx, [rbp+47h+var_88]
0x180026db9  mov     rax, [rax+90h]
0x180026dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dc5  mov     ebx, eax
0x180026dc7  test    eax, eax
0x180026dc9  js      loc_180026F0E
0x180026dcf  mov     edx, 2Fh ; '/'; Ch
0x180026dd4  mov     rcx, rdi; Str
0x180026dd7  call    cs:__imp_wcsrchr
0x180026dde  nop     dword ptr [rax+rax+00h]
0x180026de3  mov     rdx, rax
0x180026de6  test    rax, rax
0x180026de9  jnz     short loc_180026DF0
0x180026deb  mov     rdx, rdi
0x180026dee  jmp     short loc_180026DF4
0x180026df0  add     rdx, 2
0x180026df4  mov     rcx, [rbp+47h+var_80]
0x180026df8  movups  xmm0, xmmword ptr [r14]
0x180026dfc  movaps  [rbp+47h+var_50], xmm0
0x180026e00  movsd   xmm1, qword ptr [r14+10h]
0x180026e06  movsd   [rbp+47h+var_40], xmm1
0x180026e0b  mov     rax, [rcx]
0x180026e0e  lea     r8, [rbp+47h+var_70]
0x180026e12  mov     [rsp+0D0h+var_B0], r8
0x180026e17  lea     r9, [rbp+47h+var_50]
0x180026e1b  mov     r8d, r15d
0x180026e1e  mov     rax, [rax+18h]
0x180026e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e27  mov     ebx, eax
0x180026e29  test    eax, eax
0x180026e2b  js      loc_180026F0E
0x180026e31  mov     rcx, [rbp+47h+var_80]
0x180026e35  mov     rax, [rcx]
0x180026e38  lea     rdx, [rbp+47h+arg_8]
0x180026e3c  mov     rax, [rax+90h]
0x180026e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e48  mov     ebx, eax
0x180026e4a  test    eax, eax
0x180026e4c  js      loc_180026F0E
0x180026e52  mov     rax, [rsi]
0x180026e55  mov     r9d, [rbp+47h+arg_8]
0x180026e59  mov     r8d, [rbp+47h+var_88]
0x180026e5d  mov     rdx, [rbp+47h+var_80]
0x180026e61  mov     rcx, rsi
0x180026e64  mov     rax, [rax+30h]
0x180026e68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e6d  mov     ebx, eax
0x180026e6f  test    eax, eax
0x180026e71  js      loc_180026F0E
0x180026e77  mov     rdx, [rbp+47h+var_70]; struct IUnknown *
0x180026e7b  cmp     [rbp+47h+var_90], rdx
0x180026e7f  jz      short loc_180026E8A
0x180026e81  lea     rcx, [rbp+47h+var_90]; struct IUnknown **
0x180026e85  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180026e8a  mov     rcx, [rbp+47h+var_90]
0x180026e8e  mov     rax, [rcx]
0x180026e91  lea     rdx, [rbp+47h+var_88]
0x180026e95  mov     rax, [rax+90h]
0x180026e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ea1  mov     ebx, eax
0x180026ea3  test    eax, eax
0x180026ea5  js      short loc_180026F0E
0x180026ea7  mov     rcx, [rbp+47h+var_90]
0x180026eab  movups  xmm0, xmmword ptr [r14]
0x180026eaf  movaps  [rbp+47h+var_50], xmm0
0x180026eb3  movsd   xmm1, qword ptr [r14+10h]
0x180026eb9  movsd   [rbp+47h+var_40], xmm1
0x180026ebe  mov     rax, [rcx]
0x180026ec1  lea     rdx, [rbp+47h+var_50]
0x180026ec5  mov     rax, [rax+58h]
0x180026ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ece  mov     ebx, eax
0x180026ed0  test    eax, eax
0x180026ed2  js      short loc_180026F0E
0x180026ed4  mov     rcx, [rbp+47h+var_90]
0x180026ed8  mov     rax, [rcx]
0x180026edb  lea     rdx, [rbp+47h+arg_8]
0x180026edf  mov     rax, [rax+90h]
0x180026ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026eeb  mov     ebx, eax
0x180026eed  test    eax, eax
0x180026eef  js      short loc_180026F0E
0x180026ef1  mov     rax, [rsi]
0x180026ef4  mov     r9d, [rbp+47h+arg_8]
0x180026ef8  mov     r8d, [rbp+47h+var_88]
0x180026efc  mov     rdx, [rbp+47h+var_90]
0x180026f00  mov     rcx, rsi
0x180026f03  mov     rax, [rax+30h]
0x180026f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f0c  mov     ebx, eax
0x180026f0e  lea     rcx, [rbp+47h+var_70]
0x180026f12  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026f17  nop
0x180026f18  lea     rcx, [rbp+47h+var_80]
0x180026f1c  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026f21  nop
0x180026f22  lea     rcx, [rbp+47h+var_90]
0x180026f26  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180026f2b  mov     eax, ebx
0x180026f2d  add     rsp, 0A8h
0x180026f34  pop     r15
0x180026f36  pop     r14
0x180026f38  pop     rdi
0x180026f39  pop     rsi
0x180026f3a  pop     rbx
0x180026f3b  pop     rbp
0x180026f3c  retn
```
