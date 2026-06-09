# PoWdiGetCrashDumpData

- ea: `0x180001f6c`
- end: `0x18000202f`
- name: `PoWdiGetCrashDumpData`
- size: `195`
- prototype: `__int64 __fastcall(PEVENT_RECORD pEvent)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002974`

## callees

- `0x180001f6c`
- `0x1800022dc`
- `0x1800024e8`
- `0x180004930`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180001fcf`
- `msvcrt!swprintf_s` at `0x180001fcf`

## pseudocode

```c
__int64 __fastcall PoWdiGetCrashDumpData(PEVENT_RECORD pEvent, BYTE *a2, __int64 a3)
{
  unsigned int v6; // edi
  unsigned int i; // ebx
  unsigned int v8; // esi
  __int64 v9; // r8
  __int64 v11; // [rsp+30h] [rbp-88h] BYREF
  wchar_t Buffer[32]; // [rsp+40h] [rbp-78h] BYREF

  LODWORD(v11) = 0;
  v6 = 0;
  if ( PoWdiGetULongProperty(pEvent, (ULONGLONG)L"BugcheckCode", a2) && *(_DWORD *)a2 )
  {
    for ( i = 0; ; ++i )
    {
      v8 = i + 1;
      swprintf_s(Buffer, 0x20u, L"BugcheckParameter%u", i + 1);
      if ( PoWdiGetProperty(pEvent, (ULONGLONG)Buffer, v9, (BYTE *)(a3 + 8LL * i), 8u, (ULONG *)&v11)
        || (_DWORD)v11 != 8 )
      {
        break;
      }
      if ( v8 >= 4 )
        return 1;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180001f6c  push    rbx
0x180001f6e  push    rbp
0x180001f6f  push    rsi
0x180001f70  push    rdi
0x180001f71  push    r14
0x180001f73  sub     rsp, 90h
0x180001f7a  mov     rax, cs:__security_cookie
0x180001f81  xor     rax, rsp
0x180001f84  mov     [rsp+0B8h+var_38], rax
0x180001f8c  mov     r14, r8
0x180001f8f  mov     dword ptr [rsp+0B8h+var_88], 0
0x180001f97  mov     r8, rdx
0x180001f9a  mov     rbx, rdx
0x180001f9d  lea     rdx, aBugcheckcode; "BugcheckCode"
0x180001fa4  mov     rbp, rcx
0x180001fa7  xor     edi, edi
0x180001fa9  call    PoWdiGetULongProperty
0x180001fae  test    eax, eax
0x180001fb0  jz      short loc_18000200F
0x180001fb2  cmp     [rbx], edi
0x180001fb4  jz      short loc_18000200F
0x180001fb6  xor     ebx, ebx
0x180001fb8  lea     esi, [rbx+1]
0x180001fbb  mov     edx, 20h ; ' '; BufferCount
0x180001fc0  mov     r9d, esi
0x180001fc3  lea     r8, aBugcheckparame; "BugcheckParameter%u"
0x180001fca  lea     rcx, [rsp+0B8h+Buffer]; Buffer
0x180001fcf  call    cs:__imp_swprintf_s
0x180001fd5  mov     eax, ebx
0x180001fd7  lea     rdx, [rsp+0B8h+Buffer]
0x180001fdc  mov     rcx, rbp; pEvent
0x180001fdf  lea     r9, [r14+rax*8]
0x180001fe3  lea     rax, [rsp+0B8h+var_88]
0x180001fe8  mov     [rsp+0B8h+var_90], rax; __int64
0x180001fed  mov     [rsp+0B8h+var_98], 8; int
0x180001ff5  call    PoWdiGetProperty
0x180001ffa  test    eax, eax
0x180001ffc  jnz     short loc_18000200F
0x180001ffe  cmp     dword ptr [rsp+0B8h+var_88], 8
0x180002003  jnz     short loc_18000200F
0x180002005  mov     ebx, esi
0x180002007  cmp     esi, 4
0x18000200a  jb      short loc_180001FB8
0x18000200c  lea     edi, [rax+1]
0x18000200f  mov     eax, edi
0x180002011  mov     rcx, [rsp+0B8h+var_38]
0x180002019  xor     rcx, rsp; StackCookie
0x18000201c  call    __security_check_cookie
0x180002021  add     rsp, 90h
0x180002028  pop     r14
0x18000202a  pop     rdi
0x18000202b  pop     rsi
0x18000202c  pop     rbp
0x18000202d  pop     rbx
0x18000202e  retn
```
