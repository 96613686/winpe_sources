# CWapDPUHelper::AddV2Node(IConfigManager2 *,ushort const *,ConfigDataType,IResultTracker *)

- ea: `0x180025ea0`
- end: `0x1800261fd`
- name: `?AddV2Node@CWapDPUHelper@@UEAAJPEAUIConfigManager2@@PEBGW4ConfigDataType@@PEAUIResultTracker@@@Z`
- size: `861`
- prototype: `int __high(struct IConfigManager2 *, const unsigned __int16 *, enum ConfigDataType, struct IResultTracker *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001488`
- `0x180004a70`
- `0x1800110bc`
- `0x18001165c`
- `0x1800118a0`
- `0x180014330`
- `0x180025d04`
- `0x180025ea0`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025f70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180025f70`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026096`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180026096`
- `OLEAUT32!__imp_VariantInit` at `0x180025f1e`
- `OLEAUT32!__imp_VariantInit` at `0x180025f1e`
- `OLEAUT32!__imp_VariantClear` at `0x1800261ac`
- `OLEAUT32!__imp_VariantClear` at `0x1800261ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWapDPUHelper::AddV2Node(_QWORD *a1, __int64 a2, const wchar_t *a3, unsigned int a4, __int64 a5)
{
  int v9; // ebx
  __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  _QWORD *v12; // rdx
  int v13; // r8d
  int v14; // r9d
  wchar_t *v15; // rax
  __int64 v16; // rdx
  int v18; // [rsp+40h] [rbp-B8h] BYREF
  int v19; // [rsp+44h] [rbp-B4h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B0h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-A8h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-A4h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-98h] BYREF
  const wchar_t *v25; // [rsp+68h] [rbp-90h] BYREF
  const wchar_t *v26; // [rsp+70h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-80h] BYREF
  VARIANTARG v28; // [rsp+90h] [rbp-68h] BYREF

  v23 = 0;
  v20 = 0;
  v24 = 0;
  v22 = 0;
  v21 = 0;
  v18 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 && a3 && a5 )
  {
    v10 = a1[1];
    if ( (a1[2] - v10) >> 5 )
    {
      v11 = 0;
      while ( 1 )
      {
        v12 = (_QWORD *)(v10 + 32 * v11);
        if ( v12[3] > 7u )
          v12 = (_QWORD *)*v12;
        if ( !(unsigned int)_o__wcsicmp(a3, v12) )
          break;
        ++v11;
        v10 = a1[1];
        if ( v11 >= (a1[2] - v10) >> 5 )
          goto LABEL_11;
      }
      v9 = 0;
    }
    else
    {
LABEL_11:
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, a3, &v23);
      if ( v9 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 224LL))(v23, &v18);
        if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147023728 )
        {
          v9 = 0;
          if ( (unsigned int)dword_18003E080 > 5 )
          {
            v25 = L"AddV2Node";
            v26 = a3;
            v19 = v18;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              0x80000000,
              (unsigned int)&byte_1800378AF,
              v13,
              v14,
              (__int64)&v19,
              (__int64)&v26,
              (__int64)&v25);
          }
          if ( !v18 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 200LL))(v23, &v20);
            if ( v9 >= 0 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 144LL))(v20, &v22);
              if ( v9 >= 0 )
              {
                v15 = wcsrchr(a3, 0x2Fu);
                v16 = v15 ? (__int64)(v15 + 1) : (__int64)a3;
                v28 = pvarg;
                v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, VARIANTARG *, __int64 *))(*(_QWORD *)v20 + 24LL))(
                       v20,
                       v16,
                       a4,
                       &v28,
                       &v24);
                if ( v9 >= 0 )
                {
                  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 144LL))(v20, &v21);
                  if ( v9 >= 0 )
                  {
                    v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a5 + 48LL))(
                           a5,
                           v20,
                           v22,
                           v21);
                    if ( v9 >= 0 )
                    {
                      try
                      {
                        std::wstring::wstring(&v28, a3);
                        if ( a1[2] == a1[3] )
                        {
                          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a1 + 1, a1[2], &v28);
                        }
                        else
                        {
                          std::wstring::wstring(a1[2], &v28);
                          a1[2] += 32LL;
                        }
                        std::wstring::_Tidy_deallocate(&v28);
                      }
                      catch ( std::bad_alloc )
                      {
                        v19 = -2147024882;
                        v9 = -2147024882;
                      }
                    }
                  }
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
    v9 = -2147024809;
  }
  VariantClear(&pvarg);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v24);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v20);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(&v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025ea0  mov     r11, rsp
0x180025ea3  push    rbx
0x180025ea4  push    rsi
0x180025ea5  push    rdi
0x180025ea6  push    r12
0x180025ea8  push    r14
0x180025eaa  push    r15
0x180025eac  sub     rsp, 0C8h
0x180025eb3  mov     rax, cs:__security_cookie
0x180025eba  xor     rax, rsp
0x180025ebd  mov     [rsp+0F8h+var_48], rax
0x180025ec5  mov     r12d, r9d
0x180025ec8  mov     rsi, r8
0x180025ecb  mov     r14, rdx
0x180025ece  mov     rdi, rcx
0x180025ed1  mov     r15, [rsp+0F8h+arg_20]
0x180025ed9  mov     [rsp+0F8h+var_A0], 0
0x180025ee2  mov     [rsp+0F8h+var_B0], 0
0x180025eeb  mov     [rsp+0F8h+var_98], 0
0x180025ef4  mov     [rsp+0F8h+var_A4], 0
0x180025efc  mov     [rsp+0F8h+var_A8], 0
0x180025f04  mov     [rsp+0F8h+var_B8], 0
0x180025f0c  xorps   xmm0, xmm0
0x180025f0f  xor     eax, eax
0x180025f11  movups  xmmword ptr [rsp+0F8h+pvarg], xmm0
0x180025f16  mov     [r11-70h], rax
0x180025f1a  lea     rcx, [r11-80h]; pvarg
0x180025f1e  call    cs:__imp_VariantInit
0x180025f25  nop     dword ptr [rax+rax+00h]
0x180025f2a  test    r14, r14
0x180025f2d  jnz     short loc_180025F39
0x180025f2f  mov     ebx, 80070057h
0x180025f34  jmp     loc_1800261A7
0x180025f39  test    rsi, rsi
0x180025f3c  jz      short loc_180025F2F
0x180025f3e  test    r15, r15
0x180025f41  jz      short loc_180025F2F
0x180025f43  mov     rcx, [rdi+8]
0x180025f47  mov     rax, [rdi+10h]
0x180025f4b  sub     rax, rcx
0x180025f4e  sar     rax, 5
0x180025f52  test    rax, rax
0x180025f55  jz      short loc_180025F9B
0x180025f57  xor     ebx, ebx
0x180025f59  mov     rdx, rbx
0x180025f5c  shl     rdx, 5
0x180025f60  add     rdx, rcx
0x180025f63  cmp     qword ptr [rdx+18h], 7
0x180025f68  jbe     short loc_180025F6D
0x180025f6a  mov     rdx, [rdx]
0x180025f6d  mov     rcx, rsi
0x180025f70  call    cs:__imp__o__wcsicmp
0x180025f77  nop     dword ptr [rax+rax+00h]
0x180025f7c  test    eax, eax
0x180025f7e  jz      loc_1800260AF
0x180025f84  inc     rbx
0x180025f87  mov     rcx, [rdi+8]
0x180025f8b  mov     rax, [rdi+10h]
0x180025f8f  sub     rax, rcx
0x180025f92  sar     rax, 5
0x180025f96  cmp     rbx, rax
0x180025f99  jb      short loc_180025F59
0x180025f9b  mov     rax, [r14]
0x180025f9e  lea     r8, [rsp+0F8h+var_A0]
0x180025fa3  mov     rdx, rsi
0x180025fa6  mov     rcx, r14
0x180025fa9  mov     rax, [rax+50h]
0x180025fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fb2  mov     ebx, eax
0x180025fb4  test    eax, eax
0x180025fb6  js      loc_1800261A7
0x180025fbc  mov     rcx, [rsp+0F8h+var_A0]
0x180025fc1  mov     rax, [rcx]
0x180025fc4  lea     rdx, [rsp+0F8h+var_B8]
0x180025fc9  mov     rax, [rax+0E0h]
0x180025fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fd5  mov     ebx, eax
0x180025fd7  mov     ecx, 80000000h
0x180025fdc  add     eax, ecx
0x180025fde  test    ecx, eax
0x180025fe0  jnz     short loc_180025FEE
0x180025fe2  cmp     ebx, 80070490h
0x180025fe8  jnz     loc_1800261A7
0x180025fee  xor     ebx, ebx
0x180025ff0  mov     eax, cs:dword_18003E080
0x180025ff6  cmp     eax, 5
0x180025ff9  jbe     short loc_18002603E
0x180025ffb  lea     rax, aAddv2node; "AddV2Node"
0x180026002  mov     [rsp+0F8h+var_90], rax
0x180026007  mov     [rsp+0F8h+var_88], rsi
0x18002600c  mov     eax, [rsp+0F8h+var_B8]
0x180026010  mov     [rsp+0F8h+var_B4], eax
0x180026014  lea     rax, [rsp+0F8h+var_90]
0x180026019  mov     [rsp+0F8h+var_C8], rax
0x18002601e  lea     rax, [rsp+0F8h+var_88]
0x180026023  mov     [rsp+0F8h+var_D0], rax
0x180026028  lea     rax, [rsp+0F8h+var_B4]
0x18002602d  mov     [rsp+0F8h+var_D8], rax
0x180026032  lea     rdx, byte_1800378AF
0x180026039  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002603e  cmp     [rsp+0F8h+var_B8], ebx
0x180026042  jnz     loc_1800261A7
0x180026048  mov     rcx, [rsp+0F8h+var_A0]
0x18002604d  mov     rax, [rcx]
0x180026050  lea     rdx, [rsp+0F8h+var_B0]
0x180026055  mov     rax, [rax+0C8h]
0x18002605c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026061  mov     ebx, eax
0x180026063  test    eax, eax
0x180026065  js      loc_1800261A7
0x18002606b  mov     rcx, [rsp+0F8h+var_B0]
0x180026070  mov     rax, [rcx]
0x180026073  lea     rdx, [rsp+0F8h+var_A4]
0x180026078  mov     rax, [rax+90h]
0x18002607f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026084  mov     ebx, eax
0x180026086  test    eax, eax
0x180026088  js      loc_1800261A7
0x18002608e  mov     edx, 2Fh ; '/'; Ch
0x180026093  mov     rcx, rsi; Str
0x180026096  call    cs:__imp_wcsrchr
0x18002609d  nop     dword ptr [rax+rax+00h]
0x1800260a2  mov     rdx, rax
0x1800260a5  test    rax, rax
0x1800260a8  jnz     short loc_1800260B6
0x1800260aa  mov     rdx, rsi
0x1800260ad  jmp     short loc_1800260BA
0x1800260af  xor     ebx, ebx
0x1800260b1  jmp     loc_1800261A7
0x1800260b6  add     rdx, 2
0x1800260ba  mov     rcx, [rsp+0F8h+var_B0]
0x1800260bf  movups  xmm0, xmmword ptr [rsp+0F8h+pvarg]
0x1800260c4  movaps  [rsp+0F8h+var_68], xmm0
0x1800260cc  movsd   xmm1, qword ptr [rsp+0F8h+pvarg+10h]
0x1800260d5  movsd   [rsp+0F8h+var_58], xmm1
0x1800260de  mov     rax, [rcx]
0x1800260e1  lea     r8, [rsp+0F8h+var_98]
0x1800260e6  mov     [rsp+0F8h+var_D8], r8
0x1800260eb  lea     r9, [rsp+0F8h+var_68]
0x1800260f3  mov     r8d, r12d
0x1800260f6  mov     rax, [rax+18h]
0x1800260fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260ff  mov     ebx, eax
0x180026101  test    eax, eax
0x180026103  js      loc_1800261A7
0x180026109  mov     rcx, [rsp+0F8h+var_B0]
0x18002610e  mov     rax, [rcx]
0x180026111  lea     rdx, [rsp+0F8h+var_A8]
0x180026116  mov     rax, [rax+90h]
0x18002611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026122  mov     ebx, eax
0x180026124  test    eax, eax
0x180026126  js      short loc_1800261A7
0x180026128  mov     rax, [r15]
0x18002612b  mov     r9d, [rsp+0F8h+var_A8]
0x180026130  mov     r8d, [rsp+0F8h+var_A4]
0x180026135  mov     rdx, [rsp+0F8h+var_B0]
0x18002613a  mov     rcx, r15
0x18002613d  mov     rax, [rax+30h]
0x180026141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026146  mov     ebx, eax
0x180026148  test    eax, eax
0x18002614a  js      short loc_1800261A7
0x18002614c  mov     rdx, rsi
0x18002614f  lea     rcx, [rsp+0F8h+var_68]
0x180026157  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002615c  nop
0x18002615d  mov     rax, [rdi+10h]
0x180026161  cmp     rax, [rdi+18h]
0x180026165  jz      short loc_18002617E
0x180026167  lea     rdx, [rsp+0F8h+var_68]
0x18002616f  mov     rcx, rax
0x180026172  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180026177  add     qword ptr [rdi+10h], 20h ; ' '
0x18002617c  jmp     short loc_180026193
0x18002617e  lea     r8, [rsp+0F8h+var_68]
0x180026186  mov     rdx, rax
0x180026189  lea     rcx, [rdi+8]
0x18002618d  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180026192  nop
0x180026193  lea     rcx, [rsp+0F8h+var_68]; void *
0x18002619b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261a0  nop
0x1800261a1  jmp     short loc_1800261A7
0x1800261a3  mov     ebx, [rsp+0F8h+var_B4]
0x1800261a7  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x1800261ac  call    cs:__imp_VariantClear
0x1800261b3  nop     dword ptr [rax+rax+00h]
0x1800261b8  nop
0x1800261b9  lea     rcx, [rsp+0F8h+var_98]
0x1800261be  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800261c3  nop
0x1800261c4  lea     rcx, [rsp+0F8h+var_B0]
0x1800261c9  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800261ce  nop
0x1800261cf  lea     rcx, [rsp+0F8h+var_A0]
0x1800261d4  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800261d9  mov     eax, ebx
0x1800261db  mov     rcx, [rsp+0F8h+var_48]
0x1800261e3  xor     rcx, rsp; StackCookie
0x1800261e6  call    __security_check_cookie
0x1800261eb  add     rsp, 0C8h
0x1800261f2  pop     r15
0x1800261f4  pop     r14
0x1800261f6  pop     r12
0x1800261f8  pop     rdi
0x1800261f9  pop     rsi
0x1800261fa  pop     rbx
0x1800261fb  retn
```
