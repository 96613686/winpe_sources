# EapClearStateOnConfigChanged

- ea: `0x18001971c`
- end: `0x180019896`
- name: `EapClearStateOnConfigChanged`
- size: `378`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180019650`
- `0x180024750`

## callees

- `0x180005440`
- `0x180007e50`
- `0x180007f60`
- `0x180010ae0`
- `0x18001971c`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x1800197d7`
- `MobileNetworking!SetBufferAndLength` at `0x1800197d7`

## pseudocode

```c
__int64 __fastcall EapClearStateOnConfigChanged(__int64 a1)
{
  unsigned int v2; // esi
  _QWORD *v3; // rcx
  unsigned int v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx

  v2 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 304, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  if ( !(unsigned int)EapSetWorkingSetConnectionData(a1, 0, 0) )
    goto LABEL_8;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 305, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2);
LABEL_8:
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
    WPP_SF_(v3[7], 64, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v5 = SetBufferAndLength(a1 + 104, a1 + 96, 0, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_16;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v4, v5);
LABEL_16:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 66, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v7 == &WPP_GLOBAL_Control )
      return 0;
    if ( (*((_BYTE *)v7 + 68) & 1) != 0 )
    {
      WPP_SF_d(v7[7], 306, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_D(v7[7], 307, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18001971c  push    rbx
0x18001971e  push    rbp
0x18001971f  push    rsi
0x180019720  push    rdi
0x180019721  push    r14
0x180019723  push    r15
0x180019725  sub     rsp, 38h
0x180019729  mov     rax, [rcx]
0x18001972c  mov     rbx, rcx
0x18001972f  mov     esi, [rax+14h]
0x180019732  mov     rcx, cs:WPP_GLOBAL_Control
0x180019739  lea     rbp, WPP_GLOBAL_Control
0x180019740  lea     r14, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180019747  mov     r15d, 800h
0x18001974d  cmp     rcx, rbp
0x180019750  jz      short loc_180019769
0x180019752  test    [rcx+44h], r15d
0x180019756  jz      short loc_180019769
0x180019758  mov     rcx, [rcx+38h]
0x18001975c  mov     edx, 130h
0x180019761  mov     r8, r14
0x180019764  call    WPP_SF_
0x180019769  xor     r8d, r8d
0x18001976c  xor     edx, edx
0x18001976e  mov     rcx, rbx
0x180019771  call    EapSetWorkingSetConnectionData
0x180019776  test    eax, eax
0x180019778  jz      short loc_1800197A0
0x18001977a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019781  cmp     rcx, rbp
0x180019784  jz      short loc_1800197A7
0x180019786  test    byte ptr [rcx+44h], 1
0x18001978a  jz      short loc_1800197A7
0x18001978c  mov     rcx, [rcx+38h]
0x180019790  mov     edx, 131h
0x180019795  mov     r9d, esi
0x180019798  mov     r8, r14
0x18001979b  call    WPP_SF_d
0x1800197a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197a7  mov     rax, [rbx]
0x1800197aa  mov     edi, [rax+14h]
0x1800197ad  cmp     rcx, rbp
0x1800197b0  jz      short loc_1800197C9
0x1800197b2  test    [rcx+44h], r15d
0x1800197b6  jz      short loc_1800197C9
0x1800197b8  mov     rcx, [rcx+38h]
0x1800197bc  mov     edx, 40h ; '@'
0x1800197c1  mov     r8, r14
0x1800197c4  call    WPP_SF_
0x1800197c9  lea     rdx, [rbx+60h]
0x1800197cd  xor     r9d, r9d
0x1800197d0  lea     rcx, [rbx+68h]
0x1800197d4  xor     r8d, r8d
0x1800197d7  call    cs:__imp_SetBufferAndLength
0x1800197dd  mov     ebx, eax
0x1800197df  test    eax, eax
0x1800197e1  jz      short loc_180019811
0x1800197e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197ea  cmp     rcx, rbp
0x1800197ed  jz      loc_180019887
0x1800197f3  test    byte ptr [rcx+44h], 1
0x1800197f7  jz      short loc_180019818
0x1800197f9  mov     rcx, [rcx+38h]
0x1800197fd  mov     edx, 41h ; 'A'
0x180019802  mov     r9d, edi
0x180019805  mov     [rsp+68h+var_48], eax
0x180019809  mov     r8, r14
0x18001980c  call    WPP_SF_dd
0x180019811  mov     rcx, cs:WPP_GLOBAL_Control
0x180019818  cmp     rcx, rbp
0x18001981b  jz      short loc_18001983E
0x18001981d  test    [rcx+44h], r15d
0x180019821  jz      short loc_18001983E
0x180019823  mov     rcx, [rcx+38h]
0x180019827  mov     edx, 42h ; 'B'
0x18001982c  mov     r9d, ebx
0x18001982f  mov     r8, r14
0x180019832  call    WPP_SF_D
0x180019837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001983e  test    ebx, ebx
0x180019840  jz      short loc_180019868
0x180019842  cmp     rcx, rbp
0x180019845  jz      short loc_180019887
0x180019847  test    byte ptr [rcx+44h], 1
0x18001984b  jz      short loc_180019868
0x18001984d  mov     rcx, [rcx+38h]
0x180019851  mov     edx, 132h
0x180019856  mov     r9d, esi
0x180019859  mov     r8, r14
0x18001985c  call    WPP_SF_d
0x180019861  mov     rcx, cs:WPP_GLOBAL_Control
0x180019868  cmp     rcx, rbp
0x18001986b  jz      short loc_180019887
0x18001986d  test    [rcx+44h], r15d
0x180019871  jz      short loc_180019887
0x180019873  mov     rcx, [rcx+38h]
0x180019877  mov     edx, 133h
0x18001987c  xor     r9d, r9d
0x18001987f  mov     r8, r14
0x180019882  call    WPP_SF_D
0x180019887  xor     eax, eax
0x180019889  add     rsp, 38h
0x18001988d  pop     r15
0x18001988f  pop     r14
0x180019891  pop     rdi
0x180019892  pop     rsi
0x180019893  pop     rbp
0x180019894  pop     rbx
0x180019895  retn
```
