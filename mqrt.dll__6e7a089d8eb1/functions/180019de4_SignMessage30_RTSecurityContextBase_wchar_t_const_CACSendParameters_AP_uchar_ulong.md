# SignMessage30(RTSecurityContextBase *,wchar_t const *,CACSendParameters *,AP<uchar> &,ulong *)

- ea: `0x180019de4`
- end: `0x180019ecd`
- name: `?SignMessage30@@YAJPEAVRTSecurityContextBase@@PEB_WPEAVCACSendParameters@@AEAV?$AP@E@@PEAK@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c688`

## callees

- `0x18000a33c`
- `0x180019664`
- `0x180019724`
- `0x180019de4`
- `0x18001e8f0`
- `0x18001e988`
- `0x180026010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SignMessage30(DWORD *a1, BYTE *a2, __int64 a3, _QWORD *a4, DWORD *pdwSigLen)
{
  __int64 result; // rax
  ALG_ID v10; // ebx
  HCRYPTPROV v11; // rax
  HCRYPTHASH Hash; // rbx
  unsigned int v13; // eax
  const bad_CryptoApi *v14; // [rsp+20h] [rbp-28h] BYREF
  HCRYPTHASH v15; // [rsp+50h] [rbp+8h] BYREF

  result = (*(__int64 (__fastcall **)(DWORD *))(*(_QWORD *)a1 + 8LL))(a1);
  if ( (int)result >= 0 )
  {
    v10 = **(_DWORD **)(a3 + 216);
    try
    {
      v11 = (*(__int64 (**)(void))(*(_QWORD *)a1 + 16LL))();
      Hash = CryCreateHash(v11, v10);
      v15 = Hash;
      CalcPropHash(Hash, a2);
      *a4 = CryCreateSignature(Hash, a1[16], pdwSigLen);
      *(_QWORD *)(a3 + 616) = a4;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 32, &WPP_5b4ab97657783f5ca6ed00c88ea204a4_Traceguids);
      CHashHandle::~CHashHandle((CHashHandle *)&v15);
      result = 0;
    }
    catch ( const bad_CryptoApi *v14 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        v13 = (*(__int64 (__fastcall **)(const bad_CryptoApi *))(*(_QWORD *)v14 + 16LL))(v14);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 33, &WPP_5b4ab97657783f5ca6ed00c88ea204a4_Traceguids, v13);
      }
      LogMsgHR(-1072824272, (wchar_t *)L"rt/SignMqf", 0x32u);
      return 3222143024LL;
    }
    catch ( std::bad_alloc )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 34, &WPP_5b4ab97657783f5ca6ed00c88ea204a4_Traceguids);
      LogMsgHR(-1072824281, (wchar_t *)L"rt/SignMqf", 0x3Cu);
      return 3222143015LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019de4  mov     [rsp+arg_8], rbx
0x180019de9  mov     [rsp+arg_10], rsi
0x180019dee  push    rdi
0x180019def  push    r14
0x180019df1  push    r15
0x180019df3  sub     rsp, 30h
0x180019df7  mov     r14, r9
0x180019dfa  mov     rsi, r8
0x180019dfd  mov     r15, rdx
0x180019e00  mov     rdi, rcx
0x180019e03  mov     rax, [rcx]
0x180019e06  mov     rax, [rax+8]
0x180019e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e0f  test    eax, eax
0x180019e11  js      loc_180019EB8
0x180019e17  mov     rax, [rsi+0D8h]
0x180019e1e  mov     ebx, [rax]
0x180019e20  mov     rax, [rdi]
0x180019e23  mov     rcx, rdi
0x180019e26  mov     rax, [rax+10h]
0x180019e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e2f  mov     edx, ebx; unsigned int
0x180019e31  mov     rcx, rax; unsigned __int64
0x180019e34  call    ?CryCreateHash@@YA_K_KI@Z; CryCreateHash(unsigned __int64,uint)
0x180019e39  mov     rbx, rax
0x180019e3c  mov     [rsp+48h+arg_0], rax
0x180019e41  mov     r8, rsi
0x180019e44  mov     rdx, r15; pbData
0x180019e47  mov     rcx, rax; hHash
0x180019e4a  call    CalcPropHash
0x180019e4f  mov     r8, [rsp+48h+pdwSigLen]; pdwSigLen
0x180019e54  mov     edx, [rdi+40h]; dwKeySpec
0x180019e57  mov     rcx, rbx; hHash
0x180019e5a  call    ?CryCreateSignature@@YAPEAE_KKPEAK@Z; CryCreateSignature(unsigned __int64,ulong,ulong *)
0x180019e5f  mov     [r14], rax
0x180019e62  mov     [rsi+268h], r14
0x180019e69  lea     rax, WPP_GLOBAL_Control
0x180019e70  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e77  cmp     rcx, rax
0x180019e7a  jz      short loc_180019E9E
0x180019e7c  test    byte ptr [rcx+10Ch], 4
0x180019e83  jz      short loc_180019E9E
0x180019e85  mov     edx, 20h ; ' '
0x180019e8a  lea     r8, WPP_5b4ab97657783f5ca6ed00c88ea204a4_Traceguids
0x180019e91  mov     rcx, [rcx+100h]
0x180019e98  call    WPP_SF_
0x180019e9d  nop
0x180019e9e  lea     rcx, [rsp+48h+arg_0]; this
0x180019ea3  call    ??1CHashHandle@@QEAA@XZ; CHashHandle::~CHashHandle(void)
0x180019ea8  xor     eax, eax
0x180019eaa  jmp     short loc_180019EB8
0x180019eac  mov     eax, 0C00E0030h
0x180019eb1  jmp     short loc_180019EB8
0x180019eb3  mov     eax, 0C00E0027h
0x180019eb8  mov     rbx, [rsp+48h+arg_8]
0x180019ebd  mov     rsi, [rsp+48h+arg_10]
0x180019ec2  add     rsp, 30h
0x180019ec6  pop     r15
0x180019ec8  pop     r14
0x180019eca  pop     rdi
0x180019ecb  retn
```
