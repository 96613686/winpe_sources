# DataStoreServer::GetVssWriter(IIASVssWriter * *)

- ea: `0x180008b90`
- end: `0x180008cdd`
- name: `?GetVssWriter@DataStoreServer@@MEAAJPEAPEAUIIASVssWriter@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(DataStoreServer *__hidden this, struct IIASVssWriter **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002310`
- `0x180007150`
- `0x1800071ac`
- `0x180008b90`
- `0x18000d990`
- `0x180010010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008be4`
- `KERNEL32!InitializeCriticalSection` at `0x180008be4`

## string_xrefs

- `0x180008c1f`: `DataStoreServer::GetVssWriter() failed to create Vss Writer.`
- `0x180008c8c`: `DataStoreServer::GetVssWriter() failed to enable Vss Writer :%!hresult!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreServer::GetVssWriter(DataStoreServer *this, struct IIASVssWriter **a2)
{
  char *v4; // rax
  char *v5; // rbx
  int v6; // edi

  if ( !a2 )
    return 2147942487LL;
  v4 = (char *)operator new(0x48u);
  v5 = v4;
  if ( v4 )
  {
    *((_QWORD *)v4 + 1) = 0;
    *(_QWORD *)v4 = &IASVssWriter::`vftable'{for `CVssWriter'};
    *((_QWORD *)v4 + 2) = &IASVssWriter::`vftable'{for `IIASVssWriter'};
    InitializeCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
    *((_QWORD *)v5 + 8) = 0;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    v6 = (**((__int64 (__fastcall ***)(__int64))v5 + 2))((__int64)(v5 + 16));
    if ( v6 >= 0 )
    {
      *a2 = (struct IIASVssWriter *)(v5 + 16);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("DataStoreServer::GetVssWriter() failed to enable Vss Writer :%!hresult!");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
      }
      (**(void (__fastcall ***)(char *, __int64))v5)(v5, 1);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("DataStoreServer::GetVssWriter() failed to create Vss Writer.");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, "NPSDS");
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008b90  push    rbx
0x180008b92  push    rsi
0x180008b93  push    rdi
0x180008b94  push    r14
0x180008b96  sub     rsp, 38h
0x180008b9a  mov     rsi, rdx
0x180008b9d  test    rdx, rdx
0x180008ba0  jnz     short loc_180008BAC
0x180008ba2  mov     eax, 80070057h
0x180008ba7  jmp     loc_180008CD3
0x180008bac  mov     ecx, 48h ; 'H'; Size
0x180008bb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008bb6  mov     rbx, rax
0x180008bb9  mov     [rsp+58h+arg_8], rax
0x180008bbe  test    rax, rax
0x180008bc1  jz      short loc_180008BF4
0x180008bc3  mov     qword ptr [rax+8], 0
0x180008bcb  lea     rax, ??_7IASVssWriter@@6BCVssWriter@@@; const IASVssWriter::`vftable'{for `CVssWriter'}
0x180008bd2  mov     [rbx], rax
0x180008bd5  lea     rax, ??_7IASVssWriter@@6BIIASVssWriter@@@; const IASVssWriter::`vftable'{for `IIASVssWriter'}
0x180008bdc  mov     [rbx+10h], rax
0x180008be0  lea     rcx, [rbx+18h]; lpCriticalSection
0x180008be4  call    cs:__imp_InitializeCriticalSection
0x180008bea  mov     qword ptr [rbx+40h], 0
0x180008bf2  jmp     short loc_180008BF6
0x180008bf4  xor     ebx, ebx
0x180008bf6  mov     [rsp+58h+arg_8], rbx
0x180008bfb  test    rbx, rbx
0x180008bfe  jnz     short loc_180008C53
0x180008c00  lea     rcx, WPP_GLOBAL_Control
0x180008c07  mov     rax, cs:WPP_GLOBAL_Control
0x180008c0e  cmp     rax, rcx
0x180008c11  jz      short loc_180008C4C
0x180008c13  cmp     byte ptr [rax+19h], 2
0x180008c17  jb      short loc_180008C4C
0x180008c19  test    byte ptr [rax+1Ch], 10h
0x180008c1d  jz      short loc_180008C4C
0x180008c1f  lea     rcx, aDatastoreserve_12; "DataStoreServer::GetVssWriter() failed "...
0x180008c26  call    WppDbgPrint
0x180008c2b  lea     edx, [rbx+0Ah]
0x180008c2e  lea     r9, aNpsds; "NPSDS"
0x180008c35  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180008c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c43  mov     rcx, [rcx+10h]
0x180008c47  call    WPP_SF_s
0x180008c4c  mov     edi, 8007000Eh
0x180008c51  jmp     short loc_180008CD1
0x180008c53  lea     r14, [rbx+10h]
0x180008c57  mov     rax, [r14]
0x180008c5a  mov     rcx, r14
0x180008c5d  mov     rax, [rax]
0x180008c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c65  mov     edi, eax
0x180008c67  test    eax, eax
0x180008c69  jns     short loc_180008CCE
0x180008c6b  lea     rcx, WPP_GLOBAL_Control
0x180008c72  mov     rax, cs:WPP_GLOBAL_Control
0x180008c79  cmp     rax, rcx
0x180008c7c  jz      short loc_180008CB9
0x180008c7e  cmp     byte ptr [rax+19h], 2
0x180008c82  jb      short loc_180008CB9
0x180008c84  test    byte ptr [rax+1Ch], 10h
0x180008c88  jz      short loc_180008CB9
0x180008c8a  mov     edx, edi
0x180008c8c  lea     rcx, aDatastoreserve_20; "DataStoreServer::GetVssWriter() failed "...
0x180008c93  call    WppDbgPrint
0x180008c98  mov     edx, 0Bh
0x180008c9d  mov     [rsp+58h+var_38], edi
0x180008ca1  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x180008ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008caf  mov     rcx, [rcx+10h]
0x180008cb3  call    WPP_SF_sd
0x180008cb8  nop
0x180008cb9  mov     rax, [rbx]
0x180008cbc  mov     edx, 1
0x180008cc1  mov     rcx, rbx
0x180008cc4  mov     rax, [rax]
0x180008cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ccc  jmp     short loc_180008CD1
0x180008cce  mov     [rsi], r14
0x180008cd1  mov     eax, edi
0x180008cd3  add     rsp, 38h
0x180008cd7  pop     r14
0x180008cd9  pop     rdi
0x180008cda  pop     rsi
0x180008cdb  pop     rbx
0x180008cdc  retn
```
