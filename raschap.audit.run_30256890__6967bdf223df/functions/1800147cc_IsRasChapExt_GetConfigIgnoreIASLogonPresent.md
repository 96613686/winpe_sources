# IsRasChapExt_GetConfigIgnoreIASLogonPresent

- ea: `0x1800147cc`
- end: `0x18001481a`
- name: `IsRasChapExt_GetConfigIgnoreIASLogonPresent`
- size: `78`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001260`
- `0x180002040`
- `0x1800038d0`
- `0x1800042f0`
- `0x180004f50`
- `0x180005df0`
- `0x180016280`
- `0x1800172d0`
- `0x180017370`

## callees

- `0x1800147cc`
- `0x180014868`

## pseudocode

```c
char IsRasChapExt_GetConfigIgnoreIASLogonPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180033640 == 1 )
    return 1;
  if ( dword_180033640 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"@B", &v1) < 0 )
    return 0;
  result = v1;
  dword_180033640 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800147cc  sub     rsp, 28h
0x1800147d0  mov     ecx, cs:dword_180033640
0x1800147d6  sub     ecx, 1
0x1800147d9  jz      short loc_180014813
0x1800147db  cmp     ecx, 1
0x1800147de  jz      short loc_18001480F
0x1800147e0  lea     rdx, [rsp+28h+arg_0]
0x1800147e5  mov     [rsp+28h+arg_0], 0
0x1800147ea  lea     rcx, aB; "@B"
0x1800147f1  call    ApiSetQueryApiSetPresence_0
0x1800147f6  test    eax, eax
0x1800147f8  js      short loc_18001480F
0x1800147fa  mov     al, [rsp+28h+arg_0]
0x1800147fe  mov     cl, al
0x180014800  neg     cl
0x180014802  sbb     edx, edx
0x180014804  add     edx, 2
0x180014807  mov     cs:dword_180033640, edx
0x18001480d  jmp     short loc_180014815
0x18001480f  xor     al, al
0x180014811  jmp     short loc_180014815
0x180014813  mov     al, 1
0x180014815  add     rsp, 28h
0x180014819  retn
```
