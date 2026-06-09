# CopyStringW(ushort const *,unsigned __int64,ushort * *)

- ea: `0x18000ff18`
- end: `0x180010042`
- name: `?CopyStringW@@YAJPEBG_KPEAPEAG@Z`
- size: `298`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180025c90`

## callees

- `0x18000febc`
- `0x18000ff18`
- `0x180010218`
- `0x180013bd0`
- `0x1800145ec`
- `0x1800149b0`
- `0x180025468`

## string_xrefs

- `0x18000ff3e`: `CopyStringW`
- `0x18000ff58`: `CopyStringW`
- `0x18000ff7d`: `CopyStringW`
- `0x18000ffc7`: `CopyStringW`
- `0x18000fffe`: `CopyStringW`

## pseudocode

```c
__int64 __fastcall CopyStringW(const unsigned __int16 *Source, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rdi
  signed int v7; // ebx
  const unsigned __int16 *v8; // rdx
  unsigned __int64 v9; // rax
  unsigned __int16 *v10; // rax
  rsize_t v11; // r14
  unsigned int v12; // eax

  v3 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"pDest");
    v8 = L"pDest";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringW", v8);
    goto LABEL_14;
  }
  *a3 = 0;
  if ( !Source )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringW", L"source");
    v8 = L"source";
    goto LABEL_3;
  }
  v9 = 2 * (a2 + 1);
  if ( !is_mul_ok(a2 + 1, 2u) )
    v9 = -1;
  v10 = (unsigned __int16 *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v10;
  if ( v10 )
  {
    v11 = 2 * a2;
    v12 = memcpy_s_0(v10, v11, Source, v11);
    v7 = v12;
    if ( v12 )
    {
      Logger::TraceError(L"%s: wmemcpy_s failed with error code: 0x%08x.", L"CopyStringW", v12);
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      *a3 = v3;
      v7 = 0;
      v3[v11 / 2] = 0;
      v3 = 0;
    }
  }
  else
  {
    v7 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"CopyStringW");
  }
LABEL_14:
  operator delete(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ff18  push    rbx
0x18000ff1a  push    rsi
0x18000ff1b  push    rdi
0x18000ff1c  push    r14
0x18000ff1e  sub     rsp, 28h
0x18000ff22  xor     edi, edi
0x18000ff24  mov     rsi, r8
0x18000ff27  mov     r14, rdx
0x18000ff2a  mov     rbx, rcx
0x18000ff2d  test    r8, r8
0x18000ff30  jnz     short loc_18000FF69
0x18000ff32  lea     r8, aPdest; "pDest"
0x18000ff39  mov     ebx, 80070057h
0x18000ff3e  lea     rdx, aCopystringw; "CopyStringW"
0x18000ff45  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000ff4c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ff51  lea     rdx, aPdest; "pDest"
0x18000ff58  lea     rcx, aCopystringw; "CopyStringW"
0x18000ff5f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000ff64  jmp     loc_18001002E
0x18000ff69  mov     [r8], rdi
0x18000ff6c  test    rbx, rbx
0x18000ff6f  jnz     short loc_18000FF99
0x18000ff71  lea     r8, aSource; "source"
0x18000ff78  mov     ebx, 80070057h
0x18000ff7d  lea     rdx, aCopystringw; "CopyStringW"
0x18000ff84  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000ff8b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ff90  lea     rdx, aSource; "source"
0x18000ff97  jmp     short loc_18000FF58
0x18000ff99  lea     rcx, [rdx+1]
0x18000ff9d  mov     eax, 2
0x18000ffa2  mul     rcx
0x18000ffa5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ffac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ffb3  cmovb   rax, rcx
0x18000ffb7  mov     rcx, rax; unsigned __int64
0x18000ffba  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ffbf  mov     rdi, rax
0x18000ffc2  test    rax, rax
0x18000ffc5  jnz     short loc_18000FFE1
0x18000ffc7  lea     rdx, aCopystringw; "CopyStringW"
0x18000ffce  mov     ebx, 8007000Eh
0x18000ffd3  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18000ffda  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18000ffdf  jmp     short loc_18001002E
0x18000ffe1  add     r14, r14
0x18000ffe4  mov     r8, rbx; Source
0x18000ffe7  mov     r9, r14; SourceSize
0x18000ffea  mov     rdx, r14; DestinationSize
0x18000ffed  mov     rcx, rdi; Destination
0x18000fff0  call    memcpy_s_0
0x18000fff5  mov     ebx, eax
0x18000fff7  test    eax, eax
0x18000fff9  jz      short loc_180010020
0x18000fffb  mov     r8d, eax
0x18000fffe  lea     rdx, aCopystringw; "CopyStringW"
0x180010005  lea     rcx, aSWmemcpySFaile; "%s: wmemcpy_s failed with error code: 0"...
0x18001000c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180010011  test    ebx, ebx
0x180010013  jle     short loc_18001002E
0x180010015  movzx   ebx, bx
0x180010018  or      ebx, 80070000h
0x18001001e  jmp     short loc_18001002E
0x180010020  xor     ecx, ecx
0x180010022  mov     [rsi], rdi
0x180010025  xor     ebx, ebx
0x180010027  mov     [r14+rdi], cx
0x18001002c  xor     edi, edi
0x18001002e  mov     rcx, rdi; Block
0x180010031  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010036  mov     eax, ebx
0x180010038  add     rsp, 28h
0x18001003c  pop     r14
0x18001003e  pop     rdi
0x18001003f  pop     rsi
0x180010040  pop     rbx
0x180010041  retn
```
