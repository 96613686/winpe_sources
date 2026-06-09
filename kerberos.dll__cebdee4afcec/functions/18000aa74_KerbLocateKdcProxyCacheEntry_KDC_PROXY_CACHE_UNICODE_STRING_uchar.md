# KerbLocateKdcProxyCacheEntry(_KDC_PROXY_CACHE *,_UNICODE_STRING *,uchar)

- ea: `0x18000aa74`
- end: `0x18000ac24`
- name: `?KerbLocateKdcProxyCacheEntry@@YAPEAU_KDC_PROXY_CACHE_ENTRY@@PEAU_KDC_PROXY_CACHE@@PEAU_UNICODE_STRING@@E@Z`
- size: `432`
- prototype: `struct _KDC_PROXY_CACHE_ENTRY *__fastcall(struct _KDC_PROXY_CACHE *, PCUNICODE_STRING String2, unsigned __int8)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000951c`
- `0x180051720`

## callees

- `0x18000aa74`
- `0x18006bd54`
- `0x18006e748`
- `0x18008b70c`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000aaf7`
- `ntdll!RtlEqualUnicodeString` at `0x18000aaf7`
- `ntdll!RtlEnterCriticalSection` at `0x18000aaa0`
- `ntdll!RtlEnterCriticalSection` at `0x18000aaa0`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ac0a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000ac0a`

## string_xrefs

- `0x18000aab3`: `Attempted to local cache entry from uninitialized KdcProxyCache`
- `0x18000aac0`: `KerbLocateKdcProxyCacheEntry`
- `0x18000ab2e`: `KerbLocateKdcProxyCacheEntry`
- `0x18000ab97`: `KerbLocateKdcProxyCacheEntry`
- `0x18000ab21`: `found kdc proxy cache entry %p for domain %wZ\n`
- `0x18000ab8a`: `kdc proxy cache entry %p for domain %wZ is expired.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _KDC_PROXY_CACHE_ENTRY *__fastcall KerbLocateKdcProxyCacheEntry(
        struct _KDC_PROXY_CACHE *a1,
        PCUNICODE_STRING String2)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // rbp
  __int64 *i; // rbx
  struct _KDC_PROXY_CACHE_ENTRY *v7; // rdi
  char v8; // r15
  __int64 v9; // rcx
  unsigned __int128 v10; // rax

  v4 = 600000000 * KerbGlobalProxyCacheExpiry;
  RtlEnterCriticalSection(&KerbGlobalKdcProxyCacheLock);
  if ( *(_BYTE *)a1 )
  {
    v5 = v4;
    for ( i = (__int64 *)*((_QWORD *)a1 + 1); ; i = (__int64 *)*i )
    {
      v7 = 0;
      if ( i == (__int64 *)((char *)a1 + 8) )
        break;
      v7 = (struct _KDC_PROXY_CACHE_ENTRY *)i;
      v8 = 0;
      if ( RtlEqualUnicodeString((PCUNICODE_STRING)(i + 5), String2, 1u) )
      {
        v8 = 1;
        if ( i )
          v9 = WORD1(i);
        else
          v9 = 0;
        KerbTracerT::Log(
          13,
          "KerbLocateKdcProxyCacheEntry",
          686,
          "found kdc proxy cache entry %p for domain %wZ\n",
          v9,
          String2);
      }
      LOBYTE(v10) = 0;
      if ( v5 )
      {
        v10 = ((unsigned __int64)MEMORY[0x7FFE0004] << 32)
            * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8);
        LOBYTE(v10) = 0;
        if ( *((_QWORD *)&v10 + 1) > v5 && i[3] < *((_QWORD *)&v10 + 1) - v5 && (i[4] & 1) == 0 )
        {
          KerbTracerT::Log(
            13,
            "KerbLocateKdcProxyCacheEntry",
            697,
            "kdc proxy cache entry %p for domain %wZ is expired.\n",
            WORD1(i),
            i + 5);
          LOBYTE(v10) = 1;
        }
      }
      if ( v8 )
      {
        if ( !(_BYTE)v10 )
        {
          KerbReferenceKdcProxyCacheEntry(a1, (struct _KDC_PROXY_CACHE_ENTRY *)i, 0);
          break;
        }
        KerbReferenceKdcProxyCacheEntry(a1, (struct _KDC_PROXY_CACHE_ENTRY *)i, 1u);
        KerbDereferenceKdcProxyCacheEntry((struct _KDC_PROXY_CACHE_ENTRY *)i);
        goto LABEL_23;
      }
      if ( (_BYTE)v10 )
      {
        i = (__int64 *)i[1];
        KerbReferenceKdcProxyCacheEntry(a1, v7, 1u);
        KerbDereferenceKdcProxyCacheEntry(v7);
      }
    }
  }
  else
  {
    KerbTracerT::Log(
      1,
      "KerbLocateKdcProxyCacheEntry",
      666,
      "Attempted to local cache entry from uninitialized KdcProxyCache");
LABEL_23:
    v7 = 0;
  }
  RtlLeaveCriticalSection(&KerbGlobalKdcProxyCacheLock);
  return v7;
}

```

## disassembly

```asm
0x18000aa74  mov     [rsp+arg_10], r8b
0x18000aa79  push    rbx
0x18000aa7a  push    rbp
0x18000aa7b  push    rsi
0x18000aa7c  push    rdi
0x18000aa7d  push    r12
0x18000aa7f  push    r13
0x18000aa81  push    r14
0x18000aa83  push    r15
0x18000aa85  sub     rsp, 38h
0x18000aa89  mov     r13, rdx
0x18000aa8c  mov     rsi, rcx
0x18000aa8f  imul    ebx, cs:?KerbGlobalProxyCacheExpiry@@3KA, 23C34600h; ulong KerbGlobalProxyCacheExpiry
0x18000aa99  lea     rcx, ?KerbGlobalKdcProxyCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000aaa0  call    cs:__imp_RtlEnterCriticalSection
0x18000aaa6  mov     [rsp+78h+arg_11], 1
0x18000aaae  cmp     byte ptr [rsi], 0
0x18000aab1  jnz     short loc_18000AAD6
0x18000aab3  lea     r9, aAttemptedToLoc; "Attempted to local cache entry from uni"...
0x18000aaba  mov     r8d, 29Ah
0x18000aac0  lea     rdx, aKerblocatekdcp; "KerbLocateKdcProxyCacheEntry"
0x18000aac7  mov     ecx, 1
0x18000aacc  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000aad1  jmp     loc_18000AC01
0x18000aad6  mov     ebp, ebx
0x18000aad8  lea     r14, [rsi+8]
0x18000aadc  mov     rbx, [r14]
0x18000aadf  jmp     loc_18000ABD0
0x18000aae4  mov     rdi, rbx
0x18000aae7  lea     r12, [rbx+28h]
0x18000aaeb  xor     r15b, r15b
0x18000aaee  mov     r8b, 1; CaseInsensitive
0x18000aaf1  mov     rdx, r13; String2
0x18000aaf4  mov     rcx, r12; String1
0x18000aaf7  call    cs:__imp_RtlEqualUnicodeString
0x18000aafd  test    al, al
0x18000aaff  jz      short loc_18000AB3F
0x18000ab01  mov     r15b, 1
0x18000ab04  test    rbx, rbx
0x18000ab07  jz      short loc_18000AB15
0x18000ab09  mov     rax, rbx
0x18000ab0c  shr     rax, 10h
0x18000ab10  movzx   ecx, ax
0x18000ab13  jmp     short loc_18000AB17
0x18000ab15  xor     ecx, ecx
0x18000ab17  mov     [rsp+78h+var_50], r13
0x18000ab1c  mov     [rsp+78h+var_58], rcx
0x18000ab21  lea     r9, aFoundKdcProxyC; "found kdc proxy cache entry %p for doma"...
0x18000ab28  mov     r8d, 2AEh
0x18000ab2e  lea     rdx, aKerblocatekdcp; "KerbLocateKdcProxyCacheEntry"
0x18000ab35  mov     ecx, 0Dh
0x18000ab3a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000ab3f  xor     al, al
0x18000ab41  test    rbp, rbp
0x18000ab44  jz      short loc_18000ABAA
0x18000ab46  mov     ecx, ds:7FFE0004h
0x18000ab4d  mov     eax, 7FFE0320h
0x18000ab52  mov     rax, [rax]
0x18000ab55  shl     rax, 8
0x18000ab59  shl     rcx, 20h
0x18000ab5d  mul     rcx
0x18000ab60  xor     al, al
0x18000ab62  cmp     rdx, rbp
0x18000ab65  jbe     short loc_18000ABAA
0x18000ab67  sub     rdx, rbp
0x18000ab6a  cmp     [rbx+18h], rdx
0x18000ab6e  jnb     short loc_18000ABAA
0x18000ab70  test    byte ptr [rbx+20h], 1
0x18000ab74  jnz     short loc_18000ABAA
0x18000ab76  mov     rax, rbx
0x18000ab79  shr     rax, 10h
0x18000ab7d  movzx   ecx, ax
0x18000ab80  mov     [rsp+78h+var_50], r12
0x18000ab85  mov     [rsp+78h+var_58], rcx
0x18000ab8a  lea     r9, aKdcProxyCacheE; "kdc proxy cache entry %p for domain %wZ"...
0x18000ab91  mov     r8d, 2B9h
0x18000ab97  lea     rdx, aKerblocatekdcp; "KerbLocateKdcProxyCacheEntry"
0x18000ab9e  mov     ecx, 0Dh
0x18000aba3  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x18000aba8  mov     al, 1
0x18000abaa  test    r15b, r15b
0x18000abad  jnz     short loc_18000ABDD
0x18000abaf  test    al, al
0x18000abb1  jz      short loc_18000ABCD
0x18000abb3  mov     rbx, [rbx+8]
0x18000abb7  mov     r8b, 1; unsigned __int8
0x18000abba  mov     rdx, rdi; struct _KDC_PROXY_CACHE_ENTRY *
0x18000abbd  mov     rcx, rsi; struct _KDC_PROXY_CACHE *
0x18000abc0  call    ?KerbReferenceKdcProxyCacheEntry@@YAXPEAU_KDC_PROXY_CACHE@@PEAU_KDC_PROXY_CACHE_ENTRY@@E@Z; KerbReferenceKdcProxyCacheEntry(_KDC_PROXY_CACHE *,_KDC_PROXY_CACHE_ENTRY *,uchar)
0x18000abc5  mov     rcx, rdi; struct _KDC_PROXY_CACHE_ENTRY *
0x18000abc8  call    ?KerbDereferenceKdcProxyCacheEntry@@YAXPEAU_KDC_PROXY_CACHE_ENTRY@@@Z; KerbDereferenceKdcProxyCacheEntry(_KDC_PROXY_CACHE_ENTRY *)
0x18000abcd  mov     rbx, [rbx]
0x18000abd0  xor     edi, edi
0x18000abd2  cmp     rbx, r14
0x18000abd5  jnz     loc_18000AAE4
0x18000abdb  jmp     short loc_18000AC03
0x18000abdd  mov     rdx, rbx; struct _KDC_PROXY_CACHE_ENTRY *
0x18000abe0  mov     rcx, rsi; struct _KDC_PROXY_CACHE *
0x18000abe3  test    al, al
0x18000abe5  jnz     short loc_18000ABF1
0x18000abe7  xor     r8d, r8d; unsigned __int8
0x18000abea  call    ?KerbReferenceKdcProxyCacheEntry@@YAXPEAU_KDC_PROXY_CACHE@@PEAU_KDC_PROXY_CACHE_ENTRY@@E@Z; KerbReferenceKdcProxyCacheEntry(_KDC_PROXY_CACHE *,_KDC_PROXY_CACHE_ENTRY *,uchar)
0x18000abef  jmp     short loc_18000AC03
0x18000abf1  mov     r8b, 1; unsigned __int8
0x18000abf4  call    ?KerbReferenceKdcProxyCacheEntry@@YAXPEAU_KDC_PROXY_CACHE@@PEAU_KDC_PROXY_CACHE_ENTRY@@E@Z; KerbReferenceKdcProxyCacheEntry(_KDC_PROXY_CACHE *,_KDC_PROXY_CACHE_ENTRY *,uchar)
0x18000abf9  mov     rcx, rbx; struct _KDC_PROXY_CACHE_ENTRY *
0x18000abfc  call    ?KerbDereferenceKdcProxyCacheEntry@@YAXPEAU_KDC_PROXY_CACHE_ENTRY@@@Z; KerbDereferenceKdcProxyCacheEntry(_KDC_PROXY_CACHE_ENTRY *)
0x18000ac01  xor     edi, edi
0x18000ac03  lea     rcx, ?KerbGlobalKdcProxyCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000ac0a  call    cs:__imp_RtlLeaveCriticalSection
0x18000ac10  mov     rax, rdi
0x18000ac13  add     rsp, 38h
0x18000ac17  pop     r15
0x18000ac19  pop     r14
0x18000ac1b  pop     r13
0x18000ac1d  pop     r12
0x18000ac1f  pop     rdi
0x18000ac20  pop     rsi
0x18000ac21  pop     rbp
0x18000ac22  pop     rbx
0x18000ac23  retn
```
