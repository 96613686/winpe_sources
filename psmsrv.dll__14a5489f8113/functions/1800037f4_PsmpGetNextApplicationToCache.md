# PsmpGetNextApplicationToCache

- ea: `0x1800037f4`
- end: `0x18000395d`
- name: `PsmpGetNextApplicationToCache`
- size: `361`
- prototype: `volatile signed __int32 *__fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002000`

## callees

- `0x1800032a0`
- `0x1800037f4`
- `0x180009b40`
- `0x1800134d0`
- `0x180013610`
- `0x1800137a4`
- `0x18001622c`
- `0x1800192fc`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003883`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003883`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003931`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003931`

## pseudocode

```c
volatile signed __int32 *__fastcall PsmpGetNextApplicationToCache(__int64 a1, __int64 a2, __int64 a3)
{
  volatile signed __int32 *NextApplication; // rbx
  __int64 v6; // rbp
  __int64 v7; // rdi
  __int64 i; // r10
  __int64 v9; // rsi
  __int64 *v10; // r10
  _DWORD v12[4]; // [rsp+30h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-68h] BYREF
  _DWORD *v14; // [rsp+60h] [rbp-48h]
  __int64 v15; // [rsp+68h] [rbp-40h]
  _BYTE v16[16]; // [rsp+70h] [rbp-38h] BYREF

  if ( *(_BYTE *)(a1 + 48) )
  {
    if ( a3 )
      PsmpDereferenceApplicationEx(a3, 0);
    v6 = a2 + 48;
    NextApplication = 0;
    v7 = a2 + 24;
    RtlAcquireSRWLockExclusive(a2 + 48);
    for ( i = *(_QWORD *)(a2 + 24); i != v7; i = *v10 )
    {
      v9 = i - 6720;
      v12[0] = 0;
      if ( (unsigned __int8)PsmpSafeReferenceObjectEx(i - 6720, v12) )
      {
        if ( (unsigned int)dword_18003F048 > 5 && tlgKeywordOn((__int64)&dword_18003F048, 2) )
        {
          v15 = 4;
          v14 = v12;
          tlgCreate1Sz_wchar_t((__int64)v16, (char *)(v9 + 7040));
          tlgWriteTransfer_EventWriteTransfer(
            (__int64)&dword_18003F048,
            (unsigned __int8 *)word_180039012,
            0,
            0,
            4u,
            &v13);
        }
        NextApplication = (volatile signed __int32 *)v9;
        break;
      }
    }
    RtlReleaseSRWLockExclusive(v6);
  }
  else
  {
    NextApplication = PsmpGetNextApplication(a2, a3);
    if ( !NextApplication )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_b5485372ff90327e3674091dc1985471_Traceguids);
      *(_BYTE *)(a1 + 48) = 1;
    }
  }
  return NextApplication;
}

```

## disassembly

```asm
0x1800037f4  mov     [rsp+arg_18], rbx
0x1800037f9  push    rbp
0x1800037fa  push    rsi
0x1800037fb  push    rdi
0x1800037fc  sub     rsp, 90h
0x180003803  mov     rax, cs:__security_cookie
0x18000380a  xor     rax, rsp
0x18000380d  mov     [rsp+0A8h+var_28], rax
0x180003815  cmp     byte ptr [rcx+30h], 0
0x180003819  mov     rsi, rdx
0x18000381c  mov     rdi, rcx
0x18000381f  jnz     short loc_180003867
0x180003821  mov     rdx, r8
0x180003824  mov     rcx, rsi
0x180003827  call    PsmpGetNextApplication
0x18000382c  mov     rbx, rax
0x18000382f  test    rax, rax
0x180003832  jnz     loc_180003937
0x180003838  mov     rcx, cs:WPP_GLOBAL_Control
0x18000383f  test    byte ptr [rcx+1Ch], 2
0x180003843  jz      short loc_18000385E
0x180003845  cmp     byte ptr [rcx+19h], 4
0x180003849  jb      short loc_18000385E
0x18000384b  mov     rcx, [rcx+10h]
0x18000384f  lea     edx, [rax+11h]
0x180003852  lea     r8, WPP_b5485372ff90327e3674091dc1985471_Traceguids
0x180003859  call    WPP_SF_
0x18000385e  mov     byte ptr [rdi+30h], 1
0x180003862  jmp     loc_180003937
0x180003867  test    r8, r8
0x18000386a  jz      short loc_180003876
0x18000386c  xor     edx, edx
0x18000386e  mov     rcx, r8
0x180003871  call    PsmpDereferenceApplicationEx
0x180003876  lea     rbp, [rsi+30h]
0x18000387a  xor     ebx, ebx
0x18000387c  mov     rcx, rbp
0x18000387f  lea     rdi, [rsi+18h]
0x180003883  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180003889  mov     r10, [rdi]
0x18000388c  jmp     short loc_1800038AD
0x18000388e  lea     rsi, [r10-1A40h]
0x180003895  mov     [rsp+0A8h+var_78], ebx
0x180003899  mov     rcx, rsi
0x18000389c  lea     rdx, [rsp+0A8h+var_78]
0x1800038a1  call    PsmpSafeReferenceObjectEx
0x1800038a6  test    al, al
0x1800038a8  jnz     short loc_1800038B4
0x1800038aa  mov     r10, [r10]
0x1800038ad  cmp     r10, rdi
0x1800038b0  jnz     short loc_18000388E
0x1800038b2  jmp     short loc_18000392E
0x1800038b4  mov     eax, cs:dword_18003F048
0x1800038ba  cmp     eax, 5
0x1800038bd  jbe     short loc_18000392B
0x1800038bf  mov     edx, 2
0x1800038c4  lea     rcx, dword_18003F048
0x1800038cb  call    _tlgKeywordOn
0x1800038d0  test    al, al
0x1800038d2  jz      short loc_18000392B
0x1800038d4  mov     eax, [rsp+0A8h+var_78]
0x1800038d8  lea     rdx, [rsi+1B80h]
0x1800038df  mov     [rsp+0A8h+var_78], eax
0x1800038e3  lea     rcx, [rsp+0A8h+var_38]
0x1800038e8  lea     rax, [rsp+0A8h+var_78]
0x1800038ed  mov     [rsp+0A8h+var_40], 4
0x1800038f6  mov     [rsp+0A8h+var_48], rax
0x1800038fb  call    _tlgCreate1Sz_wchar_t
0x180003900  lea     r8, [rsp+0A8h+var_68]
0x180003905  xor     r9d, r9d
0x180003908  mov     [rsp+0A8h+var_80], r8
0x18000390d  lea     rdx, word_180039012
0x180003914  xor     r8d, r8d
0x180003917  mov     [rsp+0A8h+var_88], 4
0x18000391f  lea     rcx, dword_18003F048
0x180003926  call    _tlgWriteTransfer_EventWriteTransfer
0x18000392b  mov     rbx, rsi
0x18000392e  mov     rcx, rbp
0x180003931  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003937  mov     rax, rbx
0x18000393a  mov     rcx, [rsp+0A8h+var_28]
0x180003942  xor     rcx, rsp; StackCookie
0x180003945  call    __security_check_cookie
0x18000394a  mov     rbx, [rsp+0A8h+arg_18]
0x180003952  add     rsp, 90h
0x180003959  pop     rdi
0x18000395a  pop     rsi
0x18000395b  pop     rbp
0x18000395c  retn
```
