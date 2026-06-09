# NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x1800138d4`
- end: `0x180013b33`
- name: `?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `607`
- prototype: `int(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015ca4`

## callees

- `0x18000a5b4`
- `0x18000b004`
- `0x180013344`
- `0x1800138d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ac9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ac9`

## string_xrefs

- `0x180013aba`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180013ad6`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180013b0b`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::CombineSeparateStrings(
        NgcUtils *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  NgcUtils *v6; // r14
  NgcUtils *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // edi
  __int64 v11; // r9
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  unsigned __int64 v17; // rsi
  unsigned __int16 *v18; // rdi
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  _WORD *v21; // r8
  _WORD *v22; // rcx
  int v23; // eax
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  int v28; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  hMem = a2;
  v6 = this;
  if ( !this )
  {
    v10 = -2147024809;
LABEL_39:
    v14 = 179;
    goto LABEL_40;
  }
  v7 = this;
  v8 = 260;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 = (NgcUtils *)((char *)v7 + 2);
    --v8;
  }
  while ( v8 );
  v9 = -2147024809;
  v10 = v8 == 0 ? 0x80070057 : 0;
  v11 = (260 - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_39;
  v12 = 260;
  v13 = L"\\";
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  v10 = v12 == 0 ? 0x80070057 : 0;
  if ( v12 )
  {
    if ( a3 )
    {
      v15 = 260;
      v16 = a3;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v10 = v15 == 0 ? 0x80070057 : 0;
      if ( v15 )
      {
        v17 = v11
            + 1
            + ((260 - v12) & -(__int64)(v12 != 0))
            + ((260 - v15) & ((unsigned __int128)-(__int128)(unsigned __int64)v15 >> 64));
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &hMem,
          0,
          v17);
        v18 = (unsigned __int16 *)hMem;
        if ( !hMem )
        {
          v9 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC7,
            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
            (const char *)0x8007000ELL,
            v28);
          return v9;
        }
        if ( v17 )
        {
          if ( v17 > 0x7FFFFFFF )
          {
            *(_WORD *)hMem = 0;
          }
          else
          {
            v19 = 2147483646;
            v20 = v17;
            v21 = hMem;
            do
            {
              if ( !v19 )
                break;
              if ( !*(_WORD *)v6 )
                break;
              *v21 = *(_WORD *)v6;
              v6 = (NgcUtils *)((char *)v6 + 2);
              ++v21;
              --v19;
              --v20;
            }
            while ( v20 );
            v22 = v21 - 1;
            v9 = v20 == 0 ? 0x8007007A : 0;
            if ( v20 )
              v22 = v21;
            *v22 = 0;
            if ( v20 )
            {
              v23 = StringCchCatW(v18, v17, L"\\");
              v9 = v23;
              if ( v23 >= 0 )
              {
                v26 = StringCchCatW(v18, v17, a3);
                v9 = v26;
                if ( v26 >= 0 )
                {
                  *(_QWORD *)a4 = v18;
                  return 0;
                }
                v24 = (unsigned int)v26;
                v25 = 215;
              }
              else
              {
                v24 = (unsigned int)v23;
                v25 = 210;
              }
              goto LABEL_33;
            }
          }
        }
        v24 = v9;
        v25 = 205;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
          (const char *)v24,
          v28);
        LocalFree(v18);
        return v9;
      }
    }
    else
    {
      v10 = -2147024809;
    }
    v14 = 191;
    goto LABEL_40;
  }
  v14 = 185;
LABEL_40:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
    (const char *)v10,
    v28);
  return v10;
}

```

## disassembly

```asm
0x1800138d4  mov     [rsp+arg_0], rbx
0x1800138d9  mov     [rsp+arg_10], rbp
0x1800138de  mov     [rsp+hMem], rdx
0x1800138e3  push    rsi
0x1800138e4  push    rdi
0x1800138e5  push    r12
0x1800138e7  push    r14
0x1800138e9  push    r15; int
0x1800138eb  sub     rsp, 20h
0x1800138ef  xor     r12d, r12d
0x1800138f2  mov     r15, r9
0x1800138f5  mov     rbp, r8
0x1800138f8  mov     r14, rcx
0x1800138fb  test    rcx, rcx
0x1800138fe  jz      loc_180013AFC
0x180013904  mov     r10d, 104h
0x18001390a  mov     rax, rcx
0x18001390d  mov     edx, r10d
0x180013910  cmp     [rax], r12w
0x180013914  jz      short loc_180013920
0x180013916  add     rax, 2
0x18001391a  sub     rdx, 1
0x18001391e  jnz     short loc_180013910
0x180013920  mov     rax, rdx
0x180013923  mov     ebx, 80070057h
0x180013928  neg     rax
0x18001392b  mov     rcx, r10
0x18001392e  mov     rax, rdx
0x180013931  sbb     edi, edi
0x180013933  sub     rcx, rdx
0x180013936  not     edi
0x180013938  and     edi, ebx
0x18001393a  neg     rax
0x18001393d  sbb     r9, r9
0x180013940  and     r9, rcx
0x180013943  test    rdx, rdx
0x180013946  jz      loc_180013B01
0x18001394c  mov     rdx, r10
0x18001394f  lea     rax, asc_180064548; "\\"
0x180013956  cmp     [rax], r12w
0x18001395a  jz      short loc_180013966
0x18001395c  add     rax, 2
0x180013960  sub     rdx, 1
0x180013964  jnz     short loc_180013956
0x180013966  mov     rax, rdx
0x180013969  mov     rcx, r10
0x18001396c  neg     rax
0x18001396f  mov     rax, rdx
0x180013972  sbb     edi, edi
0x180013974  sub     rcx, rdx
0x180013977  not     edi
0x180013979  and     edi, ebx
0x18001397b  neg     rax
0x18001397e  sbb     r8, r8
0x180013981  and     r8, rcx
0x180013984  test    rdx, rdx
0x180013987  jnz     short loc_180013993
0x180013989  mov     edx, 0B9h
0x18001398e  jmp     loc_180013B06
0x180013993  test    rbp, rbp
0x180013996  jz      loc_180013AF3
0x18001399c  mov     rcx, r10
0x18001399f  mov     rax, rbp
0x1800139a2  cmp     [rax], r12w
0x1800139a6  jz      short loc_1800139B2
0x1800139a8  add     rax, 2
0x1800139ac  sub     rcx, 1
0x1800139b0  jnz     short loc_1800139A2
0x1800139b2  mov     rax, rcx
0x1800139b5  neg     rax
0x1800139b8  mov     rax, rcx
0x1800139bb  sbb     edi, edi
0x1800139bd  sub     r10, rcx
0x1800139c0  not     edi
0x1800139c2  and     edi, ebx
0x1800139c4  neg     rax
0x1800139c7  sbb     rdx, rdx
0x1800139ca  and     rdx, r10
0x1800139cd  test    rcx, rcx
0x1800139d0  jz      loc_180013AF5
0x1800139d6  lea     rsi, [r8+rdx]
0x1800139da  inc     r9
0x1800139dd  add     rsi, r9
0x1800139e0  lea     rcx, [rsp+48h+hMem]
0x1800139e5  mov     r8, rsi
0x1800139e8  xor     edx, edx
0x1800139ea  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800139ef  mov     rdi, [rsp+48h+hMem]
0x1800139f4  test    rdi, rdi
0x1800139f7  jz      loc_180013AD1
0x1800139fd  test    rsi, rsi
0x180013a00  jz      loc_180013AAD
0x180013a06  cmp     rsi, 7FFFFFFFh
0x180013a0d  ja      loc_180013AA9
0x180013a13  mov     eax, 7FFFFFFEh
0x180013a18  mov     rdx, rsi
0x180013a1b  mov     r8, rdi
0x180013a1e  test    rax, rax
0x180013a21  jz      short loc_180013A41
0x180013a23  movzx   ecx, word ptr [r14]
0x180013a27  test    cx, cx
0x180013a2a  jz      short loc_180013A41
0x180013a2c  mov     [r8], cx
0x180013a30  add     r14, 2
0x180013a34  add     r8, 2
0x180013a38  dec     rax
0x180013a3b  sub     rdx, 1
0x180013a3f  jnz     short loc_180013A1E
0x180013a41  mov     rax, rdx
0x180013a44  lea     rcx, [r8-2]
0x180013a48  neg     rax
0x180013a4b  sbb     ebx, ebx
0x180013a4d  not     ebx
0x180013a4f  and     ebx, 8007007Ah
0x180013a55  test    rdx, rdx
0x180013a58  cmovnz  rcx, r8
0x180013a5c  mov     [rcx], r12w
0x180013a60  jz      short loc_180013AAD
0x180013a62  lea     r8, asc_180064548; "\\"
0x180013a69  mov     rdx, rsi; unsigned __int64
0x180013a6c  mov     rcx, rdi; unsigned __int16 *
0x180013a6f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013a74  mov     ebx, eax
0x180013a76  test    eax, eax
0x180013a78  jns     short loc_180013A84
0x180013a7a  mov     r9d, eax
0x180013a7d  mov     edx, 0D2h
0x180013a82  jmp     short loc_180013AB5
0x180013a84  mov     r8, rbp; unsigned __int16 *
0x180013a87  mov     rdx, rsi; unsigned __int64
0x180013a8a  mov     rcx, rdi; unsigned __int16 *
0x180013a8d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013a92  mov     ebx, eax
0x180013a94  test    eax, eax
0x180013a96  jns     short loc_180013AA2
0x180013a98  mov     r9d, eax
0x180013a9b  mov     edx, 0D7h
0x180013aa0  jmp     short loc_180013AB5
0x180013aa2  mov     [r15], rdi
0x180013aa5  xor     eax, eax
0x180013aa7  jmp     short loc_180013B1C
0x180013aa9  mov     [rdi], r12w
0x180013aad  mov     r9d, ebx; char *
0x180013ab0  mov     edx, 0CDh; void *
0x180013ab5  mov     rcx, [rsp+48h]; this
0x180013aba  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ac6  mov     rcx, rdi; hMem
0x180013ac9  call    cs:__imp_LocalFree
0x180013acf  jmp     short loc_180013AEF
0x180013ad1  mov     rcx, [rsp+48h]; this
0x180013ad6  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013add  mov     ebx, 8007000Eh
0x180013ae2  mov     edx, 0C7h; void *
0x180013ae7  mov     r9d, ebx; char *
0x180013aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013aef  mov     eax, ebx
0x180013af1  jmp     short loc_180013B1C
0x180013af3  mov     edi, ebx
0x180013af5  mov     edx, 0BFh
0x180013afa  jmp     short loc_180013B06
0x180013afc  mov     edi, 80070057h
0x180013b01  mov     edx, 0B3h; void *
0x180013b06  mov     rcx, [rsp+48h]; this
0x180013b0b  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013b12  mov     r9d, edi; char *
0x180013b15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013b1a  mov     eax, edi
0x180013b1c  mov     rbx, [rsp+48h+arg_0]
0x180013b21  mov     rbp, [rsp+48h+arg_10]
0x180013b26  add     rsp, 20h
0x180013b2a  pop     r15
0x180013b2c  pop     r14
0x180013b2e  pop     r12
0x180013b30  pop     rdi
0x180013b31  pop     rsi
0x180013b32  retn
```
