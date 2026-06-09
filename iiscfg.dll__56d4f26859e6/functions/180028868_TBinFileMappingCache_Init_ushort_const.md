# TBinFileMappingCache::Init(ushort const *)

- ea: `0x180028868`
- end: `0x1800289ae`
- name: `?Init@TBinFileMappingCache@@AEAAJPEBG@Z`
- size: `326`
- prototype: `int(TBinFileMappingCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180026500`

## callees

- `0x180002bc4`
- `0x1800113fc`
- `0x180011b38`
- `0x180012734`
- `0x180017614`
- `0x180028868`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180028988`
- `msvcrt!wcscpy_s` at `0x180028988`
- `ole32!CoTaskMemAlloc` at `0x18002896a`
- `ole32!CoTaskMemAlloc` at `0x18002896a`

## string_xrefs

- `0x18002891c`: `inetsrv\iis\mb\config\src\stores\fixedtable\sdtfxd.cpp`

## pseudocode

```c
__int64 __fastcall TBinFileMappingCache::Init(TBinFileMappingCache *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  rsize_t v6; // rsi
  wchar_t *v7; // rax
  __int64 v8; // [rsp+88h] [rbp-60h]
  __int64 v9; // [rsp+90h] [rbp-58h]
  _BYTE v10[8]; // [rsp+B0h] [rbp-38h] BYREF
  __int64 v11; // [rsp+B8h] [rbp-30h]

  result = TFileMapping::Load((TBinFileMappingCache *)((char *)this + 8), a2);
  if ( (int)result >= 0 )
  {
    if ( FixedTableHeap::IsValid(*((FixedTableHeap **)this + 3)) )
    {
      v5 = -1;
      do
        ++v5;
      while ( a2[v5] );
      v6 = v5 + 1;
      v7 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v5 + 1, 2u));
      *(_QWORD *)this = v7;
      if ( v7 )
      {
        wcscpy_s(v7, v6, a2);
        *((_QWORD *)this + 6) = TBinFileMappingCache::m_pFirst;
        result = 0;
        TBinFileMappingCache::m_pFirst = this;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      v11 = 0;
      CErrorInterceptor::Init(
        (CErrorInterceptor *)v10,
        0,
        0,
        0x80004005,
        2u,
        -2147348295,
        a2,
        0,
        0,
        0,
        0,
        0,
        0,
        -1,
        -1,
        0,
        0,
        v8,
        v9,
        -1,
        -1);
      CErrorInterceptor::WriteToLog(
        (CErrorInterceptor *)v10,
        L"inetsrv\\iis\\mb\\config\\src\\stores\\fixedtable\\sdtfxd.cpp",
        1905,
        0x400000);
      CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v10);
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028868  push    rbx
0x18002886a  push    rbp
0x18002886b  push    rsi
0x18002886c  push    rdi
0x18002886d  sub     rsp, 0C8h
0x180028874  mov     rbx, rcx
0x180028877  mov     rdi, rdx
0x18002887a  add     rcx, 8; this
0x18002887e  call    ?Load@TFileMapping@@QEAAJPEBG_N@Z; TFileMapping::Load(ushort const *,bool)
0x180028883  xor     ebp, ebp
0x180028885  test    eax, eax
0x180028887  js      loc_1800289A2
0x18002888d  mov     rcx, [rbx+18h]; this
0x180028891  call    ?IsValid@FixedTableHeap@@QEBA_NXZ; FixedTableHeap::IsValid(void)
0x180028896  test    al, al
0x180028898  jnz     loc_180028947
0x18002889e  or      eax, 0FFFFFFFFh
0x1800288a1  mov     [rsp+0E8h+var_30], rbp
0x1800288a9  mov     [rsp+0E8h+var_48], eax
0x1800288b0  lea     rcx, [rsp+0E8h+var_38]
0x1800288b8  mov     [rsp+0E8h+var_50], eax
0x1800288bf  mov     ebx, 80004005h
0x1800288c4  mov     [rsp+0E8h+var_68], ebp
0x1800288cb  mov     r9d, ebx
0x1800288ce  mov     [rsp+0E8h+var_70], rbp
0x1800288d3  xor     r8d, r8d
0x1800288d6  mov     [rsp+0E8h+var_78], eax
0x1800288da  xor     edx, edx
0x1800288dc  mov     [rsp+0E8h+var_80], eax
0x1800288e0  mov     [rsp+0E8h+var_88], ebp
0x1800288e4  mov     [rsp+0E8h+var_90], rbp
0x1800288e9  mov     [rsp+0E8h+var_98], ebp
0x1800288ed  mov     [rsp+0E8h+var_A0], rbp
0x1800288f2  mov     [rsp+0E8h+var_A8], rbp
0x1800288f7  mov     [rsp+0E8h+var_B0], rbp
0x1800288fc  mov     [rsp+0E8h+var_B8], rdi
0x180028901  mov     [rsp+0E8h+var_C0], 800210B9h
0x180028909  mov     [rsp+0E8h+var_C8], 2
0x180028911  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x180028916  mov     r9d, 400000h; unsigned int
0x18002891c  lea     rdx, aInetsrvIisMbCo_7; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x180028923  mov     r8d, 771h; unsigned int
0x180028929  lea     rcx, [rsp+0E8h+var_38]; this
0x180028931  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x180028936  lea     rcx, [rsp+0E8h+var_38]; this
0x18002893e  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x180028943  mov     eax, ebx
0x180028945  jmp     short loc_1800289A2
0x180028947  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002894b  mov     rax, rcx
0x18002894e  inc     rax
0x180028951  cmp     [rdi+rax*2], bp
0x180028955  jnz     short loc_18002894E
0x180028957  lea     rsi, [rax+1]
0x18002895b  mov     eax, 2
0x180028960  mul     rsi
0x180028963  cmovb   rax, rcx
0x180028967  mov     rcx, rax; cb
0x18002896a  call    cs:__imp_CoTaskMemAlloc
0x180028970  mov     [rbx], rax
0x180028973  test    rax, rax
0x180028976  jnz     short loc_18002897F
0x180028978  mov     eax, 8007000Eh
0x18002897d  jmp     short loc_1800289A2
0x18002897f  mov     r8, rdi; Source
0x180028982  mov     rdx, rsi; SizeInWords
0x180028985  mov     rcx, rax; Destination
0x180028988  call    cs:__imp_wcscpy_s
0x18002898e  mov     rax, cs:?m_pFirst@TBinFileMappingCache@@0PEAV1@EA; TBinFileMappingCache * TBinFileMappingCache::m_pFirst
0x180028995  mov     [rbx+30h], rax
0x180028999  xor     eax, eax
0x18002899b  mov     cs:?m_pFirst@TBinFileMappingCache@@0PEAV1@EA, rbx; TBinFileMappingCache * TBinFileMappingCache::m_pFirst
0x1800289a2  add     rsp, 0C8h
0x1800289a9  pop     rdi
0x1800289aa  pop     rsi
0x1800289ab  pop     rbp
0x1800289ac  pop     rbx
0x1800289ad  retn
```
