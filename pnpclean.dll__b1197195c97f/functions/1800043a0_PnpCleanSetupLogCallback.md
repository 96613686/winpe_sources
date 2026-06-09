# PnpCleanSetupLogCallback

- ea: `0x1800043a0`
- end: `0x18000445a`
- name: `PnpCleanSetupLogCallback`
- size: `186`
- prototype: `void(SP_LOG_TOKEN *, int, char, CHAR *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001cd4`
- `0x180003d70`

## callees

- `0x1800043a0`
- `0x180008b98`

## import_xrefs

- `SETUPAPI!pSetupFree` at `0x18000444c`
- `SETUPAPI!pSetupFree` at `0x18000444c`
- `SETUPAPI!SetupWriteTextLog` at `0x180004443`
- `SETUPAPI!SetupWriteTextLog` at `0x180004443`

## pseudocode

```c
void PnpCleanSetupLogCallback(SP_LOG_TOKEN *a1, int a2, char a3, CHAR *a4, ...)
{
  SP_LOG_TOKEN v4; // rbx
  int v5; // ecx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  DWORD v11; // esi
  const CHAR *v12; // rax
  const CHAR *v13; // rdi
  va_list Args; // [rsp+70h] [rbp+28h] BYREF

  va_start(Args, a4);
  v4 = *a1;
  if ( *a1 == 1 )
    return;
  v5 = 2;
  if ( !v4 )
    v4 = 2;
  if ( !a2 )
    goto LABEL_16;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v5 = 1;
    goto LABEL_17;
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( !v8 )
    {
      v5 = 4;
      goto LABEL_17;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v5 = 5;
      goto LABEL_17;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v5 = 6;
      goto LABEL_17;
    }
    if ( v10 == 1 )
    {
      v5 = 7;
      goto LABEL_17;
    }
LABEL_16:
    v5 = 0;
  }
LABEL_17:
  v11 = v5 | 0x10000;
  if ( (a3 & 1) == 0 )
    v11 = v5;
  v12 = (const CHAR *)pUtilVPrintfA(a4, Args);
  v13 = v12;
  if ( v12 )
  {
    SetupWriteTextLog(v4, 0x8000000u, v11, v12, 0);
    pSetupFree(v13);
  }
}

```

## disassembly

```asm
0x1800043a0  mov     [rsp+arg_18], r9
0x1800043a5  push    rbx
0x1800043a6  push    rsi
0x1800043a7  push    rdi
0x1800043a8  sub     rsp, 30h
0x1800043ac  mov     rbx, [rcx]
0x1800043af  mov     [rsp+48h+var_28], 0
0x1800043b8  cmp     rbx, 1
0x1800043bc  jz      loc_180004452
0x1800043c2  test    rbx, rbx
0x1800043c5  mov     ecx, 2
0x1800043ca  cmovz   rbx, rcx
0x1800043ce  test    edx, edx
0x1800043d0  jz      short loc_180004411
0x1800043d2  sub     edx, 1
0x1800043d5  jz      short loc_18000440A
0x1800043d7  sub     edx, 1
0x1800043da  jz      short loc_180004413
0x1800043dc  sub     edx, 1
0x1800043df  jz      short loc_180004403
0x1800043e1  sub     edx, 1
0x1800043e4  jz      short loc_1800043FC
0x1800043e6  sub     edx, 1
0x1800043e9  jz      short loc_1800043F5
0x1800043eb  cmp     edx, 1
0x1800043ee  jnz     short loc_180004411
0x1800043f0  lea     ecx, [rdx+6]
0x1800043f3  jmp     short loc_180004413
0x1800043f5  mov     ecx, 6
0x1800043fa  jmp     short loc_180004413
0x1800043fc  mov     ecx, 5
0x180004401  jmp     short loc_180004413
0x180004403  mov     ecx, 4
0x180004408  jmp     short loc_180004413
0x18000440a  mov     ecx, 1
0x18000440f  jmp     short loc_180004413
0x180004411  xor     ecx, ecx
0x180004413  mov     esi, ecx
0x180004415  lea     rdx, [rsp+48h+Args]; Args
0x18000441a  bts     esi, 10h
0x18000441e  test    r8b, 1
0x180004422  cmovz   esi, ecx
0x180004425  mov     rcx, r9; MultiByteString
0x180004428  call    pUtilVPrintfA
0x18000442d  mov     rdi, rax
0x180004430  test    rax, rax
0x180004433  jz      short loc_180004452
0x180004435  mov     r9, rax; MessageStr
0x180004438  mov     r8d, esi; Flags
0x18000443b  mov     edx, 8000000h; Category
0x180004440  mov     rcx, rbx; LogToken
0x180004443  call    cs:__imp_SetupWriteTextLog
0x180004449  mov     rcx, rdi
0x18000444c  call    cs:__imp_pSetupFree
0x180004452  add     rsp, 30h
0x180004456  pop     rdi
0x180004457  pop     rsi
0x180004458  pop     rbx
0x180004459  retn
```
