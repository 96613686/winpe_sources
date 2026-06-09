# ___report_securityfailure

- ea: `0x1002c25f`
- end: `0x1002c32f`
- name: `___report_securityfailure`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1002c253`

## callees

- `0x1002c11b`
- `0x1002c25f`
- `0x1003cf04`

## pseudocode

```c
void __usercall __noreturn __report_securityfailure(int a1@<ebx>, int a2@<edi>, int a3@<esi>, unsigned int a4)
{
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // kr00_4
  int vars0; // [esp+31Ch] [ebp+0h]
  int retaddr; // [esp+320h] [ebp+4h]

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a4);
  dword_100444E0 = 0;
  dword_100444DC = v5;
  dword_100444D8 = v4;
  dword_100444D4 = a1;
  dword_100444D0 = a3;
  dword_100444CC = a2;
  word_100444F8 = __SS__;
  word_100444EC = __CS__;
  word_100444C8 = __DS__;
  word_100444C4 = __ES__;
  word_100444C0 = __FS__;
  word_100444BC = __GS__;
  v6 = __readeflags();
  dword_100444F0 = v6;
  dword_100444E4 = vars0;
  dword_100444E8 = retaddr;
  dword_100444F4 = (int)&a4;
  dword_100443EC = retaddr;
  dword_100443E0 = -1073740791;
  dword_100443E4 = 1;
  dword_100443F0 = 1;
  dword_100443F4 = a4;
  __raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x1002c25f  push    ebp
0x1002c260  mov     ebp, esp
0x1002c262  sub     esp, 31Ch
0x1002c268  push    17h; ProcessorFeature
0x1002c26a  call    _IsProcessorFeaturePresent@4
0x1002c26f  test    eax, eax
0x1002c271  jz      short loc_1002C278
0x1002c273  mov     ecx, [ebp+arg_0]
0x1002c276  int     29h; Win8: RtlFailFast(ecx)
0x1002c278  mov     dword_100444E0, eax
0x1002c27d  mov     dword_100444DC, ecx
0x1002c283  mov     dword_100444D8, edx
0x1002c289  mov     dword_100444D4, ebx
0x1002c28f  mov     dword_100444D0, esi
0x1002c295  mov     dword_100444CC, edi
0x1002c29b  mov     word_100444F8, ss
0x1002c2a2  mov     word_100444EC, cs
0x1002c2a9  mov     word_100444C8, ds
0x1002c2b0  mov     word_100444C4, es
0x1002c2b7  mov     word_100444C0, fs
0x1002c2be  mov     word_100444BC, gs
0x1002c2c5  pushf
0x1002c2c6  pop     dword_100444F0
0x1002c2cc  mov     eax, [ebp+var_s0]
0x1002c2cf  mov     dword_100444E4, eax
0x1002c2d4  mov     eax, [ebp+4]
0x1002c2d7  mov     dword_100444E8, eax
0x1002c2dc  lea     eax, [ebp+arg_0]
0x1002c2df  mov     dword_100444F4, eax
0x1002c2e4  mov     eax, [ebp+var_31C]
0x1002c2ea  mov     eax, dword_100444E8
0x1002c2ef  mov     dword_100443EC, eax
0x1002c2f4  mov     dword_100443E0, 0C0000409h
0x1002c2fe  mov     dword_100443E4, 1
0x1002c308  mov     dword_100443F0, 1
0x1002c312  push    4
0x1002c314  pop     eax
0x1002c315  imul    eax, 0
0x1002c318  mov     ecx, [ebp+arg_0]
0x1002c31b  mov     dword_100443F4[eax], ecx
0x1002c321  push    offset ExceptionInfo; ExceptionInfo
0x1002c326  call    ___raise_securityfailure
0x1002c32b  mov     esp, ebp
0x1002c32d  pop     ebp
0x1002c32e  retn
```
