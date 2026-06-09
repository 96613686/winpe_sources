# _AppendBodyPart(ushort *,ulong,ulong,ulong)

- ea: `0x180006f84`
- end: `0x180007091`
- name: `?_AppendBodyPart@@YAJPEAGKKK@Z`
- size: `269`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180005d44`
- `0x180007338`

## callees

- `0x180003750`
- `0x180003a20`
- `0x180006f10`
- `0x180006f84`
- `0x18000a800`

## string_xrefs

- `0x18000701f`: `ERROR: MAX_PATH < cwcPrefix. Hr=%x\n`
- `0x180007048`: `ERROR: StringCchCopy. Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _AppendBodyPart(unsigned __int16 *a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r8
  unsigned int v8; // ecx
  __int64 v9; // rax
  unsigned __int16 v11[16]; // [rsp+20h] [rbp-48h] BYREF

  v3 = a3;
  v5 = StringCchPrintfW(v11, 0xEu, L".%u");
  v6 = v5;
  if ( v5 )
  {
    v7 = "ERROR: StringCchPrintf. Hr=%x\n";
    v8 = 5182144;
LABEL_3:
    ekTraceFmt(v8, 1u, v7, v5);
    return v6;
  }
  v9 = -1;
  do
    ++v9;
  while ( v11[v9] );
  if ( (unsigned __int64)(v3 + v9) < 0x104 )
  {
    if ( (unsigned int)v3 <= 0x104 )
    {
      v5 = StringCchCopyW(&a1[v3], (unsigned int)(260 - v3), v11);
      v6 = v5;
      if ( v5 )
      {
        v7 = "ERROR: StringCchCopy. Hr=%x\n";
        v8 = 6623936;
        goto LABEL_3;
      }
      ekTraceFmt(0x6912C0u, 2u, "TRACE: BodyPartString=%ws\n", a1 + 1);
      return 0;
    }
    else
    {
      v6 = -2147024362;
      ekTraceFmt(0x5E12C0u, 1u, "ERROR: MAX_PATH < cwcPrefix. Hr=%x\n", 2147942934LL);
    }
  }
  else
  {
    v6 = -2147024774;
    ekTraceFmt(0x5612C0u, 1u, "ERROR: cwcBodyPartBuffer <= cwcPrefix + wcslen(awc). Hr=%x\n", 2147942522LL);
  }
  return v6;
}

```

## disassembly

```asm
0x180006f84  mov     [rsp+arg_8], rbx
0x180006f89  push    rbp
0x180006f8a  push    rsi
0x180006f8b  push    rdi
0x180006f8c  sub     rsp, 50h
0x180006f90  mov     rax, cs:__security_cookie
0x180006f97  xor     rax, rsp
0x180006f9a  mov     [rsp+68h+var_28], rax
0x180006f9f  mov     edi, r8d
0x180006fa2  mov     rsi, rcx
0x180006fa5  lea     r8, aU; ".%u"
0x180006fac  mov     edx, 0Eh; unsigned __int64
0x180006fb1  lea     rcx, [rsp+68h+var_48]; unsigned __int16 *
0x180006fb6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006fbb  xor     ebp, ebp
0x180006fbd  mov     ebx, eax
0x180006fbf  test    eax, eax
0x180006fc1  jz      short loc_180006FE1
0x180006fc3  lea     r8, aErrorStringcch_0; "ERROR: StringCchPrintf. Hr=%x\n"
0x180006fca  mov     ecx, 4F12C0h; unsigned int
0x180006fcf  mov     r9d, eax
0x180006fd2  mov     edx, 1; unsigned int
0x180006fd7  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180006fdc  jmp     loc_180007075
0x180006fe1  lea     rcx, [rsp+68h+var_48]
0x180006fe6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006fea  inc     rax
0x180006fed  cmp     [rcx+rax*2], bp
0x180006ff1  jnz     short loc_180006FEA
0x180006ff3  add     rax, rdi
0x180006ff6  mov     ecx, 104h
0x180006ffb  cmp     rax, rcx
0x180006ffe  jb      short loc_180007016
0x180007000  mov     ebx, 8007007Ah
0x180007005  lea     r8, aErrorCwcbodypa; "ERROR: cwcBodyPartBuffer <= cwcPrefix +"...
0x18000700c  mov     r9d, ebx
0x18000700f  mov     ecx, 5612C0h
0x180007014  jmp     short loc_180006FD2
0x180007016  cmp     edi, ecx
0x180007018  jbe     short loc_180007030
0x18000701a  mov     ebx, 80070216h
0x18000701f  lea     r8, aErrorMaxPathCw; "ERROR: MAX_PATH < cwcPrefix. Hr=%x\n"
0x180007026  mov     r9d, ebx
0x180007029  mov     ecx, 5E12C0h
0x18000702e  jmp     short loc_180006FD2
0x180007030  sub     ecx, edi
0x180007032  lea     r8, [rsp+68h+var_48]; unsigned __int16 *
0x180007037  mov     edx, ecx; unsigned __int64
0x180007039  lea     rcx, [rsi+rdi*2]; unsigned __int16 *
0x18000703d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007042  mov     ebx, eax
0x180007044  test    eax, eax
0x180007046  jz      short loc_180007059
0x180007048  lea     r8, aErrorStringcch_1; "ERROR: StringCchCopy. Hr=%x\n"
0x18000704f  mov     ecx, 6512C0h
0x180007054  jmp     loc_180006FCF
0x180007059  lea     r9, [rsi+2]
0x18000705d  mov     edx, 2; unsigned int
0x180007062  lea     r8, aTraceBodyparts; "TRACE: BodyPartString=%ws\n"
0x180007069  mov     ecx, 6912C0h; unsigned int
0x18000706e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180007073  mov     ebx, ebp
0x180007075  mov     eax, ebx
0x180007077  mov     rcx, [rsp+68h+var_28]
0x18000707c  xor     rcx, rsp; StackCookie
0x18000707f  call    __security_check_cookie
0x180007084  mov     rbx, [rsp+68h+arg_8]
0x180007089  add     rsp, 50h
0x18000708d  pop     rdi
0x18000708e  pop     rsi
0x18000708f  pop     rbp
0x180007090  retn
```
