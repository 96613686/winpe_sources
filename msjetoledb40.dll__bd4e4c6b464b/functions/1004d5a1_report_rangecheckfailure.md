# ___report_rangecheckfailure

- ea: `0x1004d5a1`
- end: `0x1004d65c`
- name: `___report_rangecheckfailure`
- size: `187`
- prototype: `void __noreturn(void)`
- caller_count: `32`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1000e140`
- `0x100118b0`
- `0x100124f0`
- `0x10022c40`
- `0x10023030`
- `0x10023ab0`
- `0x10025bf0`
- `0x10026d80`
- `0x1002ef90`
- `0x1002fa60`
- `0x10035cc0`
- `0x10035d90`
- `0x10035f80`
- `0x10036ad0`
- `0x100372f0`
- `0x10038310`
- `0x10038f10`
- `0x100395b0`
- `0x10039cc0`
- `0x1003a1a0`
- `0x1003a8b0`
- `0x1003b4c0`
- `0x1003c980`
- `0x1003d390`
- `0x1003e190`
- `0x1003eda0`
- `0x1003f730`
- `0x1003fea0`
- `0x10044ac0`
- `0x10047070`
- `0x10048e80`
- `0x1004ab50`

## callees

- `0x1004d45c`

## pseudocode

```c
void __usercall __noreturn __report_rangecheckfailure(
        int a1@<eax>,
        int a2@<edx>,
        int a3@<ecx>,
        int a4@<ebx>,
        int a5@<edi>,
        int a6@<esi>,
        int a7)
{
  unsigned int v7; // kr00_4
  int retaddr; // [esp+4h] [ebp+4h]

  dword_10051AE8 = a1;
  dword_10051AE4 = a3;
  dword_10051AE0 = a2;
  dword_10051ADC = a4;
  dword_10051AD8 = a6;
  dword_10051AD4 = a5;
  word_10051B00 = __SS__;
  word_10051AF4 = __CS__;
  word_10051AD0 = __DS__;
  word_10051ACC = __ES__;
  word_10051AC8 = __FS__;
  word_10051AC4 = __GS__;
  v7 = __readeflags();
  dword_10051AF8 = v7;
  dword_10051A38 = 65537;
  dword_10051AF0 = retaddr;
  dword_10051AFC = (int)&a7;
  dword_100519F4 = retaddr;
  dword_100519E8 = -1073740791;
  dword_100519EC = 1;
  dword_100519F8 = 1;
  dword_100519FC = 8;
  __raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1004d5a1  mov     edi, edi
0x1004d5a3  push    ebp
0x1004d5a4  mov     ebp, esp
0x1004d5a6  mov     dword_10051AE8, eax
0x1004d5ab  mov     dword_10051AE4, ecx
0x1004d5b1  mov     dword_10051AE0, edx
0x1004d5b7  mov     dword_10051ADC, ebx
0x1004d5bd  mov     dword_10051AD8, esi
0x1004d5c3  mov     dword_10051AD4, edi
0x1004d5c9  mov     word_10051B00, ss
0x1004d5d0  mov     word_10051AF4, cs
0x1004d5d7  mov     word_10051AD0, ds
0x1004d5de  mov     word_10051ACC, es
0x1004d5e5  mov     word_10051AC8, fs
0x1004d5ec  mov     word_10051AC4, gs
0x1004d5f3  pushf
0x1004d5f4  pop     dword_10051AF8
0x1004d5fa  mov     dword_10051A38, 10001h
0x1004d604  mov     eax, [ebp+4]
0x1004d607  mov     dword_10051AF0, eax
0x1004d60c  lea     eax, [ebp+4]
0x1004d60f  add     eax, 4
0x1004d612  mov     dword_10051AFC, eax
0x1004d617  mov     eax, dword_10051AF0
0x1004d61c  mov     dword_100519F4, eax
0x1004d621  mov     dword_100519E8, 0C0000409h
0x1004d62b  mov     dword_100519EC, 1
0x1004d635  mov     dword_100519F8, 1
0x1004d63f  push    4
0x1004d641  pop     eax
0x1004d642  imul    eax, 0
0x1004d645  mov     dword_100519FC[eax], 8
0x1004d64f  push    offset ExceptionInfo; ExceptionInfo
0x1004d654  call    ___raise_securityfailure
0x1004d659  nop
0x1004d65a  pop     ebp
0x1004d65b  retn
```
