# CUSTOM_PROVIDERS_CONFIG_ELEMENT::Initialize(IAppHostElement *)

- ea: `0x180044e70`
- end: `0x1800451f3`
- name: `?Initialize@CUSTOM_PROVIDERS_CONFIG_ELEMENT@@UEAAJPEAUIAppHostElement@@@Z`
- size: `899`
- prototype: `__int64 __fastcall(CUSTOM_PROVIDERS_CONFIG_ELEMENT *__hidden this, struct IAppHostElement *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180044aa0`
- `0x180044d60`

## callees

- `0x180001210`
- `0x180001250`
- `0x180001814`
- `0x18002afc4`
- `0x18002b5bc`
- `0x180044e70`
- `0x180049010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180045120`
- `OLEAUT32!__imp_SysFreeString` at `0x18004519e`
- `OLEAUT32!__imp_SysFreeString` at `0x180045120`
- `OLEAUT32!__imp_SysFreeString` at `0x18004519e`
- `OLEAUT32!__imp_VariantInit` at `0x180044ed2`
- `OLEAUT32!__imp_VariantInit` at `0x180044ed2`
- `OLEAUT32!__imp_VariantClear` at `0x18004516a`
- `OLEAUT32!__imp_VariantClear` at `0x18004516a`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18004505b`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18004505b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800450a0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800450b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800450d1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800450a0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800450b7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800450d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUSTOM_PROVIDERS_CONFIG_ELEMENT::Initialize(
        CUSTOM_PROVIDERS_CONFIG_ELEMENT *this,
        struct IAppHostElement *a2)
{
  __int64 v4; // r13
  const unsigned __int16 *v5; // rdi
  int BoolProperty; // ebx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  __int64 v8; // r14
  __int64 v9; // rax
  bool v10; // cf
  size_t v11; // rax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rbx
  LONG v14; // r15d
  int Key; // eax
  __int64 v16; // r12
  __int64 v17; // r13
  volatile signed __int32 *v18; // r14
  BSTR bstrString; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  const unsigned __int16 *v22; // [rsp+40h] [rbp-29h]
  __int64 v23; // [rsp+48h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-19h] BYREF
  VARIANTARG v25; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v26; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int16 *v27; // [rsp+E0h] [rbp+77h] BYREF
  struct IAppHostElement *v28; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = (**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
  v23 = v4;
  bstrString = 0;
  v21 = 0;
  v28 = 0;
  LODWORD(v26) = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.vt = 19;
  BoolProperty = ((__int64 (__fastcall *)(struct IAppHostElement *, __int64 *))a2->lpVtbl->get_Collection)(a2, &v21);
  if ( BoolProperty >= 0 )
  {
    BoolProperty = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v21 + 24LL))(v21, &v26);
    if ( BoolProperty >= 0 )
    {
      v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
      if ( v7 )
      {
        if ( *(v7 - 1) )
          (**v7)(v7, 3);
        else
          operator delete(v7 - 1);
        *((_QWORD *)this + 2) = 0;
      }
      v8 = (unsigned int)v26;
      v9 = 600LL * (unsigned int)v26;
      if ( !is_mul_ok((unsigned int)v26, 0x258u) )
        v9 = -1;
      v10 = __CFADD__(v9, 8);
      v11 = v9 + 8;
      if ( v10 )
        v11 = -1;
      v12 = (unsigned __int16 *)operator new(v11);
      v27 = v12;
      if ( v12 )
      {
        *(_QWORD *)v12 = v8;
        v13 = v12 + 4;
        `eh vector constructor iterator'(
          v12 + 4,
          0x258u,
          v8,
          (void (*)(void *))CUSTOM_PROVIDER_ENTRY::CUSTOM_PROVIDER_ENTRY,
          (void (*)(void *))CUSTOM_PROVIDER_ENTRY::~CUSTOM_PROVIDER_ENTRY);
      }
      else
      {
        v13 = 0;
      }
      *((_QWORD *)this + 2) = v13;
      if ( v13 )
      {
        v14 = 0;
        if ( (_DWORD)v26 )
        {
          while ( 1 )
          {
            LODWORD(v27) = 0;
            pvarg.lVal = v14;
            v25 = pvarg;
            BoolProperty = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, struct IAppHostElement **))(*(_QWORD *)v21 + 32LL))(
                             v21,
                             &v25,
                             &v28);
            if ( BoolProperty < 0 )
              break;
            BoolProperty = Config_GetBoolProperty(v28, L"enabled", (int *)&v27);
            if ( BoolProperty < 0 )
              break;
            if ( (_DWORD)v27 )
            {
              BoolProperty = Config_GetStringProperty(v28, L"name", &bstrString);
              if ( BoolProperty < 0 )
                break;
              v27 = 0;
              Key = CLKRHashTable::FindKey(v4 + 200, bstrString, &v27);
              v5 = v27;
              if ( !Key )
              {
                v16 = 600LL * *((unsigned int *)this + 2);
                v17 = *((_QWORD *)this + 2);
                v18 = (volatile signed __int32 *)*((_QWORD *)v27 + 2);
                v22 = (const unsigned __int16 *)*((_QWORD *)v27 + 33);
                v27 = (unsigned __int16 *)*((_QWORD *)v27 + 18);
                BoolProperty = STRU::Copy((STRU *)(v16 + v17 + 24), *((const unsigned __int16 **)v5 + 7));
                if ( BoolProperty >= 0
                  && (BoolProperty = STRU::Copy((STRU *)(v16 + v17 + 112), v27), BoolProperty >= 0)
                  && (BoolProperty = STRU::Copy((STRU *)(v16 + v17 + 232), v22), BoolProperty >= 0)
                  && v18 )
                {
                  _InterlockedIncrement(v18);
                  *(_QWORD *)(v16 + v17 + 16) = v18;
                }
                else if ( BoolProperty < 0 )
                {
                  break;
                }
                ++*((_DWORD *)this + 2);
                v4 = v23;
              }
            }
            if ( v28 )
            {
              ((void (__fastcall *)(struct IAppHostElement *))v28->lpVtbl->Release)(v28);
              v28 = 0;
            }
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            if ( v5 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
                (**(void (__fastcall ***)(const unsigned __int16 *, __int64))v5)(v5, 1);
              v5 = 0;
            }
            if ( ++v14 >= (unsigned int)v26 )
              goto LABEL_39;
          }
        }
        else
        {
LABEL_39:
          BoolProperty = 0;
        }
      }
      else
      {
        BoolProperty = -2147024888;
      }
    }
  }
  VariantClear(&pvarg);
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(const unsigned __int16 *, __int64))v5)(v5, 1);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v28 )
  {
    ((void (__fastcall *)(struct IAppHostElement *))v28->lpVtbl->Release)(v28);
    v28 = 0;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)BoolProperty;
}

```

## disassembly

```asm
0x180044e70  mov     [rsp-8+arg_0], rbx
0x180044e75  push    rbp
0x180044e76  push    rsi
0x180044e77  push    rdi
0x180044e78  push    r12
0x180044e7a  push    r13
0x180044e7c  push    r14
0x180044e7e  push    r15
0x180044e80  lea     rbp, [rsp-27h]
0x180044e85  sub     rsp, 90h
0x180044e8c  mov     rbx, rdx
0x180044e8f  mov     rsi, rcx
0x180044e92  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180044e99  mov     rax, [rcx]
0x180044e9c  mov     rax, [rax]
0x180044e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ea4  mov     r13, rax
0x180044ea7  mov     [rbp+57h+var_78], rax
0x180044eab  xor     r12d, r12d
0x180044eae  mov     [rbp+57h+bstrString], r12
0x180044eb2  mov     [rbp+57h+var_88], r12
0x180044eb6  mov     [rbp+57h+arg_18], r12
0x180044eba  mov     dword ptr [rbp+57h+arg_8], r12d
0x180044ebe  mov     edi, r12d
0x180044ec1  xorps   xmm0, xmm0
0x180044ec4  xor     eax, eax
0x180044ec6  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180044eca  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180044ece  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180044ed2  call    cs:__imp_VariantInit
0x180044ed8  lea     eax, [r12+13h]
0x180044edd  mov     word ptr [rbp+57h+pvarg], ax
0x180044ee1  mov     rax, [rbx]
0x180044ee4  lea     rdx, [rbp+57h+var_88]
0x180044ee8  mov     rcx, rbx
0x180044eeb  mov     rax, [rax+20h]
0x180044eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ef4  mov     ebx, eax
0x180044ef6  or      r15, 0FFFFFFFFFFFFFFFFh
0x180044efa  test    eax, eax
0x180044efc  js      loc_180045166
0x180044f02  mov     rcx, [rbp+57h+var_88]
0x180044f06  mov     rax, [rcx]
0x180044f09  lea     rdx, [rbp+57h+arg_8]
0x180044f0d  mov     rax, [rax+18h]
0x180044f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f16  mov     ebx, eax
0x180044f18  test    eax, eax
0x180044f1a  js      loc_180045166
0x180044f20  mov     rcx, [rsi+10h]
0x180044f24  test    rcx, rcx
0x180044f27  jz      short loc_180044F4E
0x180044f29  cmp     [rcx-8], r12
0x180044f2d  jz      short loc_180044F41
0x180044f2f  mov     rax, [rcx]
0x180044f32  lea     edx, [r12+3]
0x180044f37  mov     rax, [rax]
0x180044f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f3f  jmp     short loc_180044F4A
0x180044f41  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180044f45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180044f4a  mov     [rsi+10h], r12
0x180044f4e  mov     r14d, dword ptr [rbp+57h+arg_8]
0x180044f52  mov     eax, 258h
0x180044f57  mul     r14
0x180044f5a  cmovb   rax, r15
0x180044f5e  add     rax, 8
0x180044f62  cmovb   rax, r15
0x180044f66  mov     rcx, rax; Size
0x180044f69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044f6e  mov     [rbp+57h+arg_10], rax
0x180044f72  test    rax, rax
0x180044f75  jz      short loc_180044FA3
0x180044f77  mov     [rax], r14
0x180044f7a  lea     rbx, [rax+8]
0x180044f7e  lea     rax, ??1CUSTOM_PROVIDER_ENTRY@@UEAA@XZ; CUSTOM_PROVIDER_ENTRY::~CUSTOM_PROVIDER_ENTRY(void)
0x180044f85  mov     [rsp+0C0h+var_A0], rax; void (*)(void *)
0x180044f8a  lea     r9, ??0CUSTOM_PROVIDER_ENTRY@@QEAA@XZ; void (*)(void *)
0x180044f91  mov     r8d, r14d; unsigned __int64
0x180044f94  mov     edx, 258h; unsigned __int64
0x180044f99  mov     rcx, rbx; void *
0x180044f9c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180044fa1  jmp     short loc_180044FA6
0x180044fa3  mov     rbx, r12
0x180044fa6  mov     [rsi+10h], rbx
0x180044faa  test    rbx, rbx
0x180044fad  jnz     short loc_180044FB9
0x180044faf  mov     ebx, 80070008h
0x180044fb4  jmp     loc_180045166
0x180044fb9  mov     r15d, r12d
0x180044fbc  cmp     dword ptr [rbp+57h+arg_8], r12d
0x180044fc0  jbe     loc_18004515F
0x180044fc6  mov     dword ptr [rbp+57h+arg_10], r12d
0x180044fca  mov     dword ptr [rbp+57h+pvarg+8], r15d
0x180044fce  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180044fd2  movaps  [rbp+57h+var_50], xmm0
0x180044fd6  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180044fdb  movsd   [rbp+57h+var_40], xmm1
0x180044fe0  mov     rcx, [rbp+57h+var_88]
0x180044fe4  mov     rax, [rcx]
0x180044fe7  lea     r8, [rbp+57h+arg_18]
0x180044feb  lea     rdx, [rbp+57h+var_50]
0x180044fef  mov     rax, [rax+20h]
0x180044ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ff8  mov     ebx, eax
0x180044ffa  test    eax, eax
0x180044ffc  js      loc_180045162
0x180045002  lea     r8, [rbp+57h+arg_10]; int *
0x180045006  lea     rdx, aEnabled; "enabled"
0x18004500d  mov     rcx, [rbp+57h+arg_18]; struct IAppHostElement *
0x180045011  call    ?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z; Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)
0x180045016  mov     ebx, eax
0x180045018  test    eax, eax
0x18004501a  js      loc_180045162
0x180045020  cmp     dword ptr [rbp+57h+arg_10], r12d
0x180045024  jz      loc_1800450FE
0x18004502a  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x18004502e  lea     rdx, aName; "name"
0x180045035  mov     rcx, [rbp+57h+arg_18]; struct IAppHostElement *
0x180045039  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x18004503e  mov     ebx, eax
0x180045040  test    eax, eax
0x180045042  js      loc_180045162
0x180045048  mov     [rbp+57h+arg_10], r12
0x18004504c  lea     rcx, [r13+0C8h]
0x180045053  lea     r8, [rbp+57h+arg_10]
0x180045057  mov     rdx, [rbp+57h+bstrString]
0x18004505b  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180045061  mov     rdi, [rbp+57h+arg_10]
0x180045065  test    eax, eax
0x180045067  jnz     loc_1800450FE
0x18004506d  mov     eax, [rsi+8]
0x180045070  imul    r12, rax, 258h
0x180045077  mov     r13, [rsi+10h]
0x18004507b  mov     r14, [rdi+10h]
0x18004507f  mov     rax, [rdi+108h]
0x180045086  mov     [rbp+57h+var_80], rax
0x18004508a  mov     rax, [rdi+90h]
0x180045091  mov     [rbp+57h+arg_10], rax
0x180045095  lea     rcx, [r13+18h]
0x180045099  add     rcx, r12
0x18004509c  mov     rdx, [rdi+38h]
0x1800450a0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800450a6  mov     ebx, eax
0x1800450a8  test    eax, eax
0x1800450aa  js      short loc_1800450F0
0x1800450ac  lea     rcx, [r13+70h]
0x1800450b0  add     rcx, r12
0x1800450b3  mov     rdx, [rbp+57h+arg_10]
0x1800450b7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800450bd  mov     ebx, eax
0x1800450bf  test    eax, eax
0x1800450c1  js      short loc_1800450F0
0x1800450c3  lea     rcx, [r13+0E8h]
0x1800450ca  add     rcx, r12
0x1800450cd  mov     rdx, [rbp+57h+var_80]
0x1800450d1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800450d7  mov     ebx, eax
0x1800450d9  test    eax, eax
0x1800450db  js      short loc_1800450F0
0x1800450dd  test    r14, r14
0x1800450e0  jz      short loc_1800450F0
0x1800450e2  lock inc dword ptr [r14]
0x1800450e6  mov     [r12+r13+10h], r14
0x1800450eb  xor     r12d, r12d
0x1800450ee  jmp     short loc_1800450F7
0x1800450f0  xor     r12d, r12d
0x1800450f3  test    ebx, ebx
0x1800450f5  js      short loc_180045162
0x1800450f7  inc     dword ptr [rsi+8]
0x1800450fa  mov     r13, [rbp+57h+var_78]
0x1800450fe  mov     rcx, [rbp+57h+arg_18]
0x180045102  test    rcx, rcx
0x180045105  jz      short loc_180045117
0x180045107  mov     rax, [rcx]
0x18004510a  mov     rax, [rax+10h]
0x18004510e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045113  mov     [rbp+57h+arg_18], r12
0x180045117  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18004511b  test    rcx, rcx
0x18004511e  jz      short loc_18004512A
0x180045120  call    cs:__imp_SysFreeString
0x180045126  mov     [rbp+57h+bstrString], r12
0x18004512a  test    rdi, rdi
0x18004512d  jz      short loc_180045152
0x18004512f  or      eax, 0FFFFFFFFh
0x180045132  lock xadd [rdi+0Ch], eax
0x180045137  cmp     eax, 1
0x18004513a  jnz     short loc_18004514F
0x18004513c  mov     rax, [rdi]
0x18004513f  mov     edx, 1
0x180045144  mov     rcx, rdi
0x180045147  mov     rax, [rax]
0x18004514a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004514f  mov     rdi, r12
0x180045152  inc     r15d
0x180045155  cmp     r15d, dword ptr [rbp+57h+arg_8]
0x180045159  jb      loc_180044FC6
0x18004515f  mov     ebx, r12d
0x180045162  or      r15, 0FFFFFFFFFFFFFFFFh
0x180045166  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004516a  call    cs:__imp_VariantClear
0x180045170  test    rdi, rdi
0x180045173  jz      short loc_180045195
0x180045175  mov     eax, r15d
0x180045178  lock xadd [rdi+0Ch], eax
0x18004517d  add     eax, r15d
0x180045180  jnz     short loc_180045195
0x180045182  mov     rax, [rdi]
0x180045185  mov     edx, 1
0x18004518a  mov     rcx, rdi
0x18004518d  mov     rax, [rax]
0x180045190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045195  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180045199  test    rcx, rcx
0x18004519c  jz      short loc_1800451A8
0x18004519e  call    cs:__imp_SysFreeString
0x1800451a4  mov     [rbp+57h+bstrString], r12
0x1800451a8  mov     rcx, [rbp+57h+arg_18]
0x1800451ac  test    rcx, rcx
0x1800451af  jz      short loc_1800451C1
0x1800451b1  mov     rax, [rcx]
0x1800451b4  mov     rax, [rax+10h]
0x1800451b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451bd  mov     [rbp+57h+arg_18], r12
0x1800451c1  mov     rcx, [rbp+57h+var_88]
0x1800451c5  test    rcx, rcx
0x1800451c8  jz      short loc_1800451D6
0x1800451ca  mov     rax, [rcx]
0x1800451cd  mov     rax, [rax+10h]
0x1800451d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451d6  mov     eax, ebx
0x1800451d8  mov     rbx, [rsp+0C0h+arg_0]
0x1800451e0  add     rsp, 90h
0x1800451e7  pop     r15
0x1800451e9  pop     r14
0x1800451eb  pop     r13
0x1800451ed  pop     r12
0x1800451ef  pop     rdi
0x1800451f0  pop     rsi
0x1800451f1  pop     rbp
0x1800451f2  retn
```
