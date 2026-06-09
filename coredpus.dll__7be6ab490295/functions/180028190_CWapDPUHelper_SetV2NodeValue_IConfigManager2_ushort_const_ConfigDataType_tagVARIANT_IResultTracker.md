# CWapDPUHelper::SetV2NodeValue(IConfigManager2 *,ushort const *,ConfigDataType,tagVARIANT,IResultTracker *)

- ea: `0x180028190`
- end: `0x180028425`
- name: `?SetV2NodeValue@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGW4ConfigDataType@@UtagVARIANT@@PEAUIResultTracker@@@Z`
- size: `661`
- prototype: `int __high(struct IConfigManager2 *, const unsigned __int16 *, enum ConfigDataType, struct tagVARIANT, struct IResultTracker *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001488`
- `0x1800110bc`
- `0x180028190`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800282e8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800282e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWapDPUHelper::SetV2NodeValue(
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
  __int64 v12; // rax
  wchar_t *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  unsigned int v17; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v18; // [rsp+48h] [rbp-21h] BYREF
  int v19; // [rsp+50h] [rbp-19h] BYREF
  __int64 v20; // [rsp+58h] [rbp-11h] BYREF
  int v21; // [rsp+60h] [rbp-9h] BYREF
  __int64 v22; // [rsp+68h] [rbp-1h] BYREF
  const OLECHAR *v23; // [rsp+70h] [rbp+7h] BYREF
  const OLECHAR *v24; // [rsp+78h] [rbp+Fh] BYREF
  __int128 v25; // [rsp+80h] [rbp+17h] BYREF
  __int64 v26; // [rsp+90h] [rbp+27h]
  unsigned int v27; // [rsp+C8h] [rbp+5Fh] BYREF

  v18 = 0;
  v20 = 0;
  v22 = 0;
  v17 = 0;
  v27 = 0;
  v19 = 0;
  if ( a2 && a3 && (v9 = a6) != 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, const OLECHAR *, __int64 **))(*(_QWORD *)a2 + 80LL))(a2, a3, &v18);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v18 + 224))(v18, &v19);
      if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147023728 )
      {
        if ( (unsigned int)dword_18003E080 > 5 )
        {
          v23 = L"SetV2NodeValue";
          v24 = a3;
          v21 = v19;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            0x80000000LL,
            (unsigned __int8 *)byte_18003778B,
            v10,
            v11,
            (__int64)&v21,
            &v24,
            &v23);
        }
        v12 = *v18;
        if ( v19 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v12 + 144))(v18, &v17);
          if ( v8 >= 0 )
          {
            v25 = *a5;
            v26 = *((_QWORD *)a5 + 2);
            v8 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, _QWORD))(*v18 + 96))(v18, &v25, a4);
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v18 + 144))(v18, &v27);
              if ( v8 >= 0 )
              {
                v15 = (__int64)v18;
                goto LABEL_23;
              }
            }
          }
        }
        else
        {
          v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v12 + 200))(v18, &v20);
          if ( v8 >= 0 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 144LL))(v20, &v17);
            if ( v8 >= 0 )
            {
              v13 = wcsrchr(a3, 0x2Fu);
              v14 = v13 ? (__int64)(v13 + 1) : (__int64)a3;
              v25 = *a5;
              v26 = *((_QWORD *)a5 + 2);
              v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, __int64 *))(*(_QWORD *)v20 + 24LL))(
                     v20,
                     v14,
                     a4,
                     &v25,
                     &v22);
              if ( v8 >= 0 )
              {
                v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 144LL))(v20, &v27);
                if ( v8 >= 0 )
                {
                  v15 = v20;
LABEL_23:
                  v8 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v9 + 48LL))(
                         v9,
                         v15,
                         v17,
                         v27);
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v22);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v20);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180028190  mov     [rsp-8+arg_0], rbx
0x180028195  mov     [rsp-8+arg_10], rsi
0x18002819a  push    rbp
0x18002819b  push    rdi
0x18002819c  push    r14
0x18002819e  lea     rbp, [rsp-37h]
0x1800281a3  sub     rsp, 0A0h
0x1800281aa  mov     r14d, r9d
0x1800281ad  mov     rdi, r8
0x1800281b0  mov     r10, rdx
0x1800281b3  mov     [rbp+47h+var_68], 0
0x1800281bb  mov     [rbp+47h+var_58], 0
0x1800281c3  mov     [rbp+47h+var_48], 0
0x1800281cb  mov     [rbp+47h+var_70], 0
0x1800281d2  mov     [rbp+47h+arg_8], 0
0x1800281d9  mov     [rbp+47h+var_60], 0
0x1800281e0  test    rdx, rdx
0x1800281e3  jnz     short loc_1800281EF
0x1800281e5  mov     ebx, 80070057h
0x1800281ea  jmp     loc_1800283ED
0x1800281ef  test    rdi, rdi
0x1800281f2  jz      short loc_1800281E5
0x1800281f4  mov     rsi, [rbp+47h+arg_28]
0x1800281f8  test    rsi, rsi
0x1800281fb  jz      short loc_1800281E5
0x1800281fd  mov     rax, [rdx]
0x180028200  lea     r8, [rbp+47h+var_68]
0x180028204  mov     rdx, rdi
0x180028207  mov     rcx, r10
0x18002820a  mov     rax, [rax+50h]
0x18002820e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028213  mov     ebx, eax
0x180028215  test    eax, eax
0x180028217  js      loc_1800283ED
0x18002821d  mov     rcx, [rbp+47h+var_68]
0x180028221  mov     rax, [rcx]
0x180028224  lea     rdx, [rbp+47h+var_60]
0x180028228  mov     rax, [rax+0E0h]
0x18002822f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028234  mov     ebx, eax
0x180028236  mov     ecx, 80000000h
0x18002823b  add     eax, ecx
0x18002823d  test    ecx, eax
0x18002823f  jnz     short loc_18002824D
0x180028241  cmp     ebx, 80070490h
0x180028247  jnz     loc_1800283ED
0x18002824d  mov     eax, cs:dword_18003E080
0x180028253  cmp     eax, 5
0x180028256  jbe     short loc_180028294
0x180028258  lea     rax, aSetv2nodevalue; "SetV2NodeValue"
0x18002825f  mov     [rbp+47h+var_40], rax
0x180028263  mov     [rbp+47h+var_38], rdi
0x180028267  mov     eax, [rbp+47h+var_60]
0x18002826a  mov     [rbp+47h+var_50], eax
0x18002826d  lea     rax, [rbp+47h+var_40]
0x180028271  mov     [rsp+0B0h+var_80], rax
0x180028276  lea     rax, [rbp+47h+var_38]
0x18002827a  mov     [rsp+0B0h+var_88], rax
0x18002827f  lea     rax, [rbp+47h+var_50]
0x180028283  mov     [rsp+0B0h+var_90], rax
0x180028288  lea     rdx, byte_18003778B
0x18002828f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180028294  mov     rcx, [rbp+47h+var_68]
0x180028298  mov     rax, [rcx]
0x18002829b  cmp     [rbp+47h+var_60], 0
0x18002829f  jnz     loc_18002836B
0x1800282a5  lea     rdx, [rbp+47h+var_58]
0x1800282a9  mov     rax, [rax+0C8h]
0x1800282b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282b5  mov     ebx, eax
0x1800282b7  test    eax, eax
0x1800282b9  js      loc_1800283ED
0x1800282bf  mov     rcx, [rbp+47h+var_58]
0x1800282c3  mov     rax, [rcx]
0x1800282c6  lea     rdx, [rbp+47h+var_70]
0x1800282ca  mov     rax, [rax+90h]
0x1800282d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282d6  mov     ebx, eax
0x1800282d8  test    eax, eax
0x1800282da  js      loc_1800283ED
0x1800282e0  mov     edx, 2Fh ; '/'; Ch
0x1800282e5  mov     rcx, rdi; Str
0x1800282e8  call    cs:__imp_wcsrchr
0x1800282ef  nop     dword ptr [rax+rax+00h]
0x1800282f4  mov     rdx, rax
0x1800282f7  test    rax, rax
0x1800282fa  jnz     short loc_180028301
0x1800282fc  mov     rdx, rdi
0x1800282ff  jmp     short loc_180028305
0x180028301  add     rdx, 2
0x180028305  mov     rcx, [rbp+47h+var_58]
0x180028309  mov     rax, [rbp+47h+arg_20]
0x18002830d  movups  xmm0, xmmword ptr [rax]
0x180028310  movaps  [rbp+47h+var_30], xmm0
0x180028314  movsd   xmm1, qword ptr [rax+10h]
0x180028319  movsd   [rbp+47h+var_20], xmm1
0x18002831e  mov     rax, [rcx]
0x180028321  lea     r8, [rbp+47h+var_48]
0x180028325  mov     [rsp+0B0h+var_90], r8
0x18002832a  lea     r9, [rbp+47h+var_30]
0x18002832e  mov     r8d, r14d
0x180028331  mov     rax, [rax+18h]
0x180028335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002833a  mov     ebx, eax
0x18002833c  test    eax, eax
0x18002833e  js      loc_1800283ED
0x180028344  mov     rcx, [rbp+47h+var_58]
0x180028348  mov     rax, [rcx]
0x18002834b  lea     rdx, [rbp+47h+arg_8]
0x18002834f  mov     rax, [rax+90h]
0x180028356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002835b  mov     ebx, eax
0x18002835d  test    eax, eax
0x18002835f  js      loc_1800283ED
0x180028365  mov     rdx, [rbp+47h+var_58]
0x180028369  jmp     short loc_1800283D4
0x18002836b  lea     rdx, [rbp+47h+var_70]
0x18002836f  mov     rax, [rax+90h]
0x180028376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002837b  mov     ebx, eax
0x18002837d  test    eax, eax
0x18002837f  js      short loc_1800283ED
0x180028381  mov     rcx, [rbp+47h+var_68]
0x180028385  mov     rax, [rbp+47h+arg_20]
0x180028389  movups  xmm0, xmmword ptr [rax]
0x18002838c  movaps  [rbp+47h+var_30], xmm0
0x180028390  movsd   xmm1, qword ptr [rax+10h]
0x180028395  movsd   [rbp+47h+var_20], xmm1
0x18002839a  mov     rax, [rcx]
0x18002839d  mov     r8d, r14d
0x1800283a0  lea     rdx, [rbp+47h+var_30]
0x1800283a4  mov     rax, [rax+60h]
0x1800283a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283ad  mov     ebx, eax
0x1800283af  test    eax, eax
0x1800283b1  js      short loc_1800283ED
0x1800283b3  mov     rcx, [rbp+47h+var_68]
0x1800283b7  mov     rax, [rcx]
0x1800283ba  lea     rdx, [rbp+47h+arg_8]
0x1800283be  mov     rax, [rax+90h]
0x1800283c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283ca  mov     ebx, eax
0x1800283cc  test    eax, eax
0x1800283ce  js      short loc_1800283ED
0x1800283d0  mov     rdx, [rbp+47h+var_68]
0x1800283d4  mov     rax, [rsi]
0x1800283d7  mov     r9d, [rbp+47h+arg_8]
0x1800283db  mov     r8d, [rbp+47h+var_70]
0x1800283df  mov     rcx, rsi
0x1800283e2  mov     rax, [rax+30h]
0x1800283e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283eb  mov     ebx, eax
0x1800283ed  lea     rcx, [rbp+47h+var_48]
0x1800283f1  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800283f6  nop
0x1800283f7  lea     rcx, [rbp+47h+var_58]
0x1800283fb  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x180028400  nop
0x180028401  lea     rcx, [rbp+47h+var_68]
0x180028405  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002840a  mov     eax, ebx
0x18002840c  lea     r11, [rsp+0B0h+var_10]
0x180028414  mov     rbx, [r11+20h]
0x180028418  mov     rsi, [r11+30h]
0x18002841c  mov     rsp, r11
0x18002841f  pop     r14
0x180028421  pop     rdi
0x180028422  pop     rbp
0x180028423  retn
```
