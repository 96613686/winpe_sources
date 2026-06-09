# VarCreate

- ea: `0x14000dcf8`
- end: `0x14000deb8`
- name: `VarCreate`
- size: `448`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x140001cf0`
- `0x1400054b0`
- `0x140007934`
- `0x14000e028`

## callees

- `0x140008620`
- `0x14000ce88`
- `0x14000dcf8`
- `0x14000e138`
- `0x14000e1a4`
- `0x14000e1f4`
- `0x14000e450`

## import_xrefs

- `msvcrt!malloc` at `0x14000dd8d`
- `msvcrt!malloc` at `0x14000dd8d`
- `msvcrt!free` at `0x14000de2b`
- `msvcrt!free` at `0x14000de3a`
- `msvcrt!free` at `0x14000de43`
- `msvcrt!free` at `0x14000de2b`
- `msvcrt!free` at `0x14000de3a`
- `msvcrt!free` at `0x14000de43`
- `msvcrt!_strdup` at `0x14000ddd3`
- `msvcrt!_strdup` at `0x14000ddd3`

## string_xrefs

- `0x14000dd5a`: `[INTERR] Variable already created: %1`
- `0x14000de5e`: `attempting to create variable: %1`

## pseudocode

```c
_DWORD *__fastcall VarCreate(_QWORD *a1, const char *a2, __int64 a3, int a4, int a5, __int64 a6, __int64 a7)
{
  const char *v11; // r9
  const char *v12; // rdx
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  char *v15; // rax
  _DWORD *result; // rax
  void *v17; // rcx
  _BYTE v18[512]; // [rsp+30h] [rbp-238h] BYREF

  if ( !(unsigned int)isValidVarName(a2, a7) )
    return 0;
  if ( findVar(a1, a2, a7) )
  {
    v11 = a2;
    v12 = "[INTERR] Variable already created: %1";
    goto LABEL_18;
  }
  *(_DWORD *)(a7 + 512) = 0;
  *(_BYTE *)a7 = 0;
  *(_DWORD *)(a7 + 544) = 0;
  *(_QWORD *)(a7 + 552) = 0;
  v13 = malloc(0x38u);
  v14 = v13;
  if ( !v13 )
  {
LABEL_16:
    if ( *(_DWORD *)(a7 + 512) )
      return 0;
    MsgSet(v18, 512, "attempting to create variable: %1", "%s", a2);
    v11 = v18;
    v12 = "Out of memory: %1";
LABEL_18:
    ErrSet(a7, v12, "%s", v11);
    return 0;
  }
  v13[5] = a5;
  *((_QWORD *)v13 + 3) = a6;
  *(_QWORD *)v13 = 0;
  *((_QWORD *)v13 + 1) = 0;
  v13[4] = a4;
  *((_QWORD *)v13 + 6) = 0;
  v15 = _strdup(a2);
  *(_QWORD *)v14 = v15;
  if ( !v15 || !(unsigned int)setVarValue(v14, a3, a7) )
  {
    if ( *(_QWORD *)v14 )
      free(*(void **)v14);
    v17 = (void *)*((_QWORD *)v14 + 1);
    if ( v17 )
      free(v17);
    free(v14);
    goto LABEL_16;
  }
  *((_QWORD *)v14 + 4) = 0;
  *((_QWORD *)v14 + 5) = a1[1];
  if ( *a1 )
    *(_QWORD *)(a1[1] + 32LL) = v14;
  else
    *a1 = v14;
  a1[1] = v14;
  result = v14;
  *((_QWORD *)v14 + 6) = a1;
  return result;
}

```

## disassembly

```asm
0x14000dcf8  mov     [rsp+arg_18], rbx
0x14000dcfd  push    rbp
0x14000dcfe  push    rsi
0x14000dcff  push    rdi
0x14000dd00  push    r14
0x14000dd02  push    r15
0x14000dd04  sub     rsp, 240h
0x14000dd0b  mov     rax, cs:__security_cookie
0x14000dd12  xor     rax, rsp
0x14000dd15  mov     [rsp+268h+var_38], rax
0x14000dd1d  mov     rsi, [rsp+268h+arg_30]
0x14000dd25  mov     rbp, rdx
0x14000dd28  mov     rdi, rcx
0x14000dd2b  mov     rdx, rsi
0x14000dd2e  mov     rcx, rbp
0x14000dd31  mov     r14d, r9d
0x14000dd34  mov     r15, r8
0x14000dd37  call    isValidVarName
0x14000dd3c  test    eax, eax
0x14000dd3e  jz      loc_14000DE8F
0x14000dd44  mov     r8, rsi
0x14000dd47  mov     rdx, rbp
0x14000dd4a  mov     rcx, rdi
0x14000dd4d  call    findVar
0x14000dd52  test    rax, rax
0x14000dd55  jz      short loc_14000DD66
0x14000dd57  mov     r9, rbp
0x14000dd5a  lea     rdx, aInterrVariable; "[INTERR] Variable already created: %1"
0x14000dd61  jmp     loc_14000DE80
0x14000dd66  mov     dword ptr [rsi+200h], 0
0x14000dd70  mov     ecx, 38h ; '8'; Size
0x14000dd75  mov     byte ptr [rsi], 0
0x14000dd78  mov     dword ptr [rsi+220h], 0
0x14000dd82  mov     qword ptr [rsi+228h], 0
0x14000dd8d  call    cs:__imp_malloc
0x14000dd93  mov     rbx, rax
0x14000dd96  test    rax, rax
0x14000dd99  jz      loc_14000DE49
0x14000dd9f  mov     ecx, [rsp+268h+arg_20]
0x14000dda6  mov     [rax+14h], ecx
0x14000dda9  mov     rcx, [rsp+268h+arg_28]
0x14000ddb1  mov     [rax+18h], rcx
0x14000ddb5  mov     rcx, rbp; Source
0x14000ddb8  mov     qword ptr [rax], 0
0x14000ddbf  mov     qword ptr [rax+8], 0
0x14000ddc7  mov     [rax+10h], r14d
0x14000ddcb  mov     qword ptr [rax+30h], 0
0x14000ddd3  call    cs:__imp__strdup
0x14000ddd9  mov     [rbx], rax
0x14000dddc  test    rax, rax
0x14000dddf  jz      short loc_14000DE23
0x14000dde1  mov     r8, rsi
0x14000dde4  mov     rdx, r15
0x14000dde7  mov     rcx, rbx
0x14000ddea  call    setVarValue
0x14000ddef  test    eax, eax
0x14000ddf1  jz      short loc_14000DE23
0x14000ddf3  mov     qword ptr [rbx+20h], 0
0x14000ddfb  mov     rax, [rdi+8]
0x14000ddff  mov     [rbx+28h], rax
0x14000de03  cmp     qword ptr [rdi], 0
0x14000de07  jnz     short loc_14000DE0E
0x14000de09  mov     [rdi], rbx
0x14000de0c  jmp     short loc_14000DE16
0x14000de0e  mov     rax, [rdi+8]
0x14000de12  mov     [rax+20h], rbx
0x14000de16  mov     [rdi+8], rbx
0x14000de1a  mov     rax, rbx
0x14000de1d  mov     [rbx+30h], rdi
0x14000de21  jmp     short loc_14000DE91
0x14000de23  mov     rcx, [rbx]; Block
0x14000de26  test    rcx, rcx
0x14000de29  jz      short loc_14000DE31
0x14000de2b  call    cs:__imp_free
0x14000de31  mov     rcx, [rbx+8]; Block
0x14000de35  test    rcx, rcx
0x14000de38  jz      short loc_14000DE40
0x14000de3a  call    cs:__imp_free
0x14000de40  mov     rcx, rbx; Block
0x14000de43  call    cs:__imp_free
0x14000de49  cmp     dword ptr [rsi+200h], 0
0x14000de50  jnz     short loc_14000DE8F
0x14000de52  lea     r9, aS_4; "%s"
0x14000de59  mov     [rsp+268h+var_248], rbp
0x14000de5e  lea     r8, aAttemptingToCr_0; "attempting to create variable: %1"
0x14000de65  mov     edx, 200h
0x14000de6a  lea     rcx, [rsp+268h+var_238]
0x14000de6f  call    MsgSet
0x14000de74  lea     r9, [rsp+268h+var_238]
0x14000de79  lea     rdx, aOutOfMemory1_0; "Out of memory: %1"
0x14000de80  lea     r8, aS_4; "%s"
0x14000de87  mov     rcx, rsi
0x14000de8a  call    ErrSet
0x14000de8f  xor     eax, eax
0x14000de91  mov     rcx, [rsp+268h+var_38]
0x14000de99  xor     rcx, rsp; StackCookie
0x14000de9c  call    __security_check_cookie
0x14000dea1  mov     rbx, [rsp+268h+arg_18]
0x14000dea9  add     rsp, 240h
0x14000deb0  pop     r15
0x14000deb2  pop     r14
0x14000deb4  pop     rdi
0x14000deb5  pop     rsi
0x14000deb6  pop     rbp
0x14000deb7  retn
```
