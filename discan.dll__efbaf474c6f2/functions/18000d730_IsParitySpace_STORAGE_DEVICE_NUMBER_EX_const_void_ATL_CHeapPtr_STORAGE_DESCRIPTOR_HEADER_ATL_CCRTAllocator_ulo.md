# IsParitySpace(_STORAGE_DEVICE_NUMBER_EX const *,void *,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &)

- ea: `0x18000d730`
- end: `0x18000d9b4`
- name: `?IsParitySpace@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXAEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z`
- size: `644`
- prototype: `__int64 __fastcall(__int64, void *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800148f4`
- `0x18001548c`

## callees

- `0x1800032f8`
- `0x1800064d8`
- `0x180006688`
- `0x18000d730`
- `0x18000f890`
- `0x1800105d8`
- `0x180012578`
- `0x180037620`

## import_xrefs

- `ntdll!RtlEqualString` at `0x18000d968`
- `ntdll!RtlEqualString` at `0x18000d968`

## pseudocode

```c
__int64 __fastcall IsParitySpace(__int64 a1, void *a2, _QWORD *a3, __int64 a4)
{
  __int64 v8; // rdx
  USHORT Length; // cx
  USHORT v10; // r8
  USHORT v11; // ax
  int v12; // eax
  unsigned int v13; // ebx
  _DWORD *v14; // rbx
  unsigned __int64 v15; // r8
  _DWORD *v16; // rcx
  int v17; // edx
  int v18; // r8d
  PVOID *v19; // rcx
  unsigned __int64 v21; // [rsp+30h] [rbp-40h] BYREF
  STRING String2; // [rsp+38h] [rbp-38h] BYREF
  const char *v23; // [rsp+48h] [rbp-28h] BYREF
  int v24; // [rsp+50h] [rbp-20h]
  __int64 InputBuffer; // [rsp+58h] [rbp-18h] BYREF
  int v26; // [rsp+60h] [rbp-10h]

  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  Length = GlobalIndentString.Length;
  v23 = "IsParitySpace";
  v10 = ++*(_WORD *)(v8 + 8);
  *(_QWORD *)(v8 + 16) = "IsParitySpace";
  v11 = Length;
  if ( v10 < Length )
  {
    v11 = v10;
    Length = v10;
  }
  String2.Length = v11;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Buffer = off_180047060;
  String2.MaximumLength = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"IsParitySpace");
  }
  InputBuffer = 14;
  v26 = 0;
  LODWORD(v21) = 0;
  v12 = StorageQueryProperty(a2, &InputBuffer, a4, (__int64)&v21);
  v24 = v12;
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = (_DWORD *)*a3;
    if ( *(_DWORD *)*a3 == 32 && v14[1] == (_DWORD)v21 )
    {
      if ( !v14[2] )
        goto LABEL_29;
      v15 = (unsigned int)v14[2];
      v16 = (_DWORD *)*a3;
      String2 = 0;
      SafeGetAnsiStringFromBuffer(v16, (unsigned int)v21, v15, &String2);
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DaZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, *(_DWORD *)(a1 + 16), (__int64)&String2);
          v19 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v19 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
          {
            WPP_SF_Dd(v19[2], 73, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, *(unsigned int *)(a1 + 16), v14[4]);
            v19 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
            WPP_SF_Dd(v19[2], 74, &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids, *(unsigned int *)(a1 + 16), v14[3]);
        }
      }
      if ( RtlEqualString(&ParitySpaceName, &String2, 1u) )
      {
        v24 = 0;
        v13 = 0;
      }
      else
      {
LABEL_29:
        v24 = 1;
        v13 = 1;
      }
    }
    else
    {
      v13 = -2147024883;
      v24 = -2147024883;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      &WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
      *(unsigned int *)(a1 + 16),
      v12);
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v23);
  return v13;
}

```

## disassembly

```asm
0x18000d730  push    rbp
0x18000d732  push    rbx
0x18000d733  push    rsi
0x18000d734  push    rdi
0x18000d735  push    r13
0x18000d737  push    r14
0x18000d739  push    r15
0x18000d73b  mov     rbp, rsp
0x18000d73e  sub     rsp, 70h
0x18000d742  mov     rax, cs:__security_cookie
0x18000d749  xor     rax, rsp
0x18000d74c  mov     [rbp+var_8], rax
0x18000d750  mov     rax, gs:58h
0x18000d759  mov     rdi, rcx
0x18000d75c  mov     ecx, cs:_tls_index
0x18000d762  mov     rsi, r8
0x18000d765  mov     r8d, 8
0x18000d76b  mov     rbx, rdx
0x18000d76e  mov     r15d, 1
0x18000d774  mov     r14, r9
0x18000d777  lea     r9, aIsparityspace; "IsParitySpace"
0x18000d77e  mov     rdx, [rax+rcx*8]
0x18000d782  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000d789  mov     eax, 10h
0x18000d78e  mov     [rbp+var_28], r9
0x18000d792  add     [r8+rdx], r15w
0x18000d797  movzx   r8d, word ptr [r8+rdx]
0x18000d79c  mov     [rax+rdx], r9
0x18000d7a0  cmp     r8w, cx
0x18000d7a4  movzx   eax, cx
0x18000d7a7  cmovb   ax, r8w
0x18000d7ac  cmovb   cx, r8w
0x18000d7b1  mov     [rbp+String2.Length], ax
0x18000d7b5  xor     eax, eax
0x18000d7b7  mov     dword ptr [rbp+String2+4], eax
0x18000d7ba  mov     rax, cs:off_180047060; "                                       "...
0x18000d7c1  mov     [rbp+String2.Buffer], rax
0x18000d7c5  mov     [rbp+String2.MaximumLength], cx
0x18000d7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7d0  lea     r13, WPP_GLOBAL_Control
0x18000d7d7  cmp     rcx, r13
0x18000d7da  jz      short loc_18000D7FE
0x18000d7dc  test    [rcx+1Ch], r15b
0x18000d7e0  jz      short loc_18000D7FE
0x18000d7e2  cmp     byte ptr [rcx+19h], 5
0x18000d7e6  jb      short loc_18000D7FE
0x18000d7e8  mov     rcx, [rcx+10h]; LoggerHandle
0x18000d7ec  lea     edx, [r15+0Ch]
0x18000d7f0  mov     [rsp+70h+var_50], r9; __int64
0x18000d7f5  lea     r9, [rbp+String2]
0x18000d7f9  call    WPP_SF_aZs
0x18000d7fe  xor     eax, eax
0x18000d800  mov     [rbp+InputBuffer], 0Eh
0x18000d808  mov     [rbp+var_10], eax
0x18000d80b  lea     rdx, [rbp+InputBuffer]; InputBuffer
0x18000d80f  mov     dword ptr [rbp+var_40], eax
0x18000d812  mov     r9, rsi
0x18000d815  lea     rax, [rbp+var_40]
0x18000d819  mov     rcx, rbx; Handle
0x18000d81c  mov     [rsp+70h+var_48], rax; __int64
0x18000d821  mov     [rsp+70h+var_50], r14; __int64
0x18000d826  call    ?StorageQueryProperty@@YAJPEAXPEBU_STORAGE_PROPERTY_QUERY@@KAEAV?$CHeapPtr@U_STORAGE_DESCRIPTOR_HEADER@@VCCRTAllocator@ATL@@@ATL@@AEAKPEAK@Z; StorageQueryProperty(void *,_STORAGE_PROPERTY_QUERY const *,ulong,ATL::CHeapPtr<_STORAGE_DESCRIPTOR_HEADER,ATL::CCRTAllocator> &,ulong &,ulong *)
0x18000d82b  mov     [rbp+var_20], eax
0x18000d82e  mov     ebx, eax
0x18000d830  test    eax, eax
0x18000d832  jns     short loc_18000D87A
0x18000d834  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d83b  cmp     rcx, r13
0x18000d83e  jz      loc_18000D98E
0x18000d844  test    [rcx+1Ch], r15b
0x18000d848  jz      loc_18000D98E
0x18000d84e  cmp     byte ptr [rcx+19h], 2
0x18000d852  jb      loc_18000D98E
0x18000d858  mov     r9d, [rdi+10h]
0x18000d85c  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000d863  mov     rcx, [rcx+10h]
0x18000d867  mov     edx, 47h ; 'G'
0x18000d86c  mov     dword ptr [rsp+70h+var_50], eax
0x18000d870  call    WPP_SF_Dd
0x18000d875  jmp     loc_18000D98E
0x18000d87a  mov     rbx, [rsi]
0x18000d87d  cmp     dword ptr [rbx], 20h ; ' '
0x18000d880  jnz     loc_18000D986
0x18000d886  mov     eax, dword ptr [rbp+var_40]
0x18000d889  cmp     [rbx+4], eax
0x18000d88c  jnz     loc_18000D986
0x18000d892  cmp     dword ptr [rbx+8], 0
0x18000d896  jbe     loc_18000D97D
0x18000d89c  mov     r8d, [rbx+8]; unsigned __int64
0x18000d8a0  lea     r9, [rbp+String2]; struct _STRING *
0x18000d8a4  xorps   xmm0, xmm0
0x18000d8a7  mov     edx, eax; unsigned __int64
0x18000d8a9  mov     rcx, rbx; void *
0x18000d8ac  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18000d8b0  call    ?SafeGetAnsiStringFromBuffer@@YAJPEBX_K1PEAU_STRING@@@Z; SafeGetAnsiStringFromBuffer(void const *,unsigned __int64,unsigned __int64,_STRING *)
0x18000d8b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8bc  cmp     rcx, r13
0x18000d8bf  jz      loc_18000D95A
0x18000d8c5  mov     sil, 4
0x18000d8c8  test    [rcx+1Ch], r15b
0x18000d8cc  jz      short loc_18000D8F1
0x18000d8ce  cmp     [rcx+19h], sil
0x18000d8d2  jb      short loc_18000D8F1
0x18000d8d4  mov     r9d, [rdi+10h]
0x18000d8d8  lea     rax, [rbp+String2]
0x18000d8dc  mov     rcx, [rcx+10h]
0x18000d8e0  mov     [rsp+70h+var_50], rax
0x18000d8e5  call    WPP_SF_DaZ
0x18000d8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8f1  cmp     rcx, r13
0x18000d8f4  jz      short loc_18000D95A
0x18000d8f6  test    [rcx+1Ch], r15b
0x18000d8fa  jz      short loc_18000D929
0x18000d8fc  cmp     [rcx+19h], sil
0x18000d900  jb      short loc_18000D929
0x18000d902  mov     eax, [rbx+10h]
0x18000d905  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000d90c  mov     r9d, [rdi+10h]
0x18000d910  mov     edx, 49h ; 'I'
0x18000d915  mov     rcx, [rcx+10h]
0x18000d919  mov     dword ptr [rsp+70h+var_50], eax
0x18000d91d  call    WPP_SF_Dd
0x18000d922  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d929  cmp     rcx, r13
0x18000d92c  jz      short loc_18000D95A
0x18000d92e  test    [rcx+1Ch], r15b
0x18000d932  jz      short loc_18000D95A
0x18000d934  cmp     [rcx+19h], sil
0x18000d938  jb      short loc_18000D95A
0x18000d93a  mov     eax, [rbx+0Ch]
0x18000d93d  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000d944  mov     r9d, [rdi+10h]
0x18000d948  mov     edx, 4Ah ; 'J'
0x18000d94d  mov     rcx, [rcx+10h]
0x18000d951  mov     dword ptr [rsp+70h+var_50], eax
0x18000d955  call    WPP_SF_Dd
0x18000d95a  mov     r8b, r15b; CaseInSensitive
0x18000d95d  lea     rdx, [rbp+String2]; String2
0x18000d961  lea     rcx, ?ParitySpaceName@@3U_STRING@@B; String1
0x18000d968  call    cs:__imp_RtlEqualString
0x18000d96e  test    al, al
0x18000d970  jz      short loc_18000D97D
0x18000d972  mov     [rbp+var_20], 0
0x18000d979  xor     ebx, ebx
0x18000d97b  jmp     short loc_18000D98E
0x18000d97d  mov     [rbp+var_20], r15d
0x18000d981  mov     ebx, r15d
0x18000d984  jmp     short loc_18000D98E
0x18000d986  mov     ebx, 8007000Dh
0x18000d98b  mov     [rbp+var_20], ebx
0x18000d98e  lea     rcx, [rbp+var_28]; this
0x18000d992  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000d997  mov     eax, ebx
0x18000d999  mov     rcx, [rbp+var_8]
0x18000d99d  xor     rcx, rsp; StackCookie
0x18000d9a0  call    __security_check_cookie
0x18000d9a5  add     rsp, 70h
0x18000d9a9  pop     r15
0x18000d9ab  pop     r14
0x18000d9ad  pop     r13
0x18000d9af  pop     rdi
0x18000d9b0  pop     rsi
0x18000d9b1  pop     rbx
0x18000d9b2  pop     rbp
0x18000d9b3  retn
```
