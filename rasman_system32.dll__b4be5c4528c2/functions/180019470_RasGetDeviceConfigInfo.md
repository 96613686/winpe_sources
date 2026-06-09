# RasGetDeviceConfigInfo

- ea: `0x180019470`
- end: `0x18001958e`
- name: `RasGetDeviceConfigInfo`
- size: `286`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180011f80`
- `0x180012330`
- `0x180019470`
- `0x180021b14`
- `0x180021fd4`

## pseudocode

```c
__int64 __fastcall RasGetDeviceConfigInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int v13; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 555, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( (unsigned int)ValidateConnectionHandle(a1) )
  {
    v13 = SubmitRequest(a1, 0x5Fu, a2, a4, a5, a3);
    v9 = v13;
    if ( !v13 )
    {
LABEL_16:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v11 = 557;
    v12 = v13;
LABEL_15:
    WPP_SF_d(v10[2], v11, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
    goto LABEL_16;
  }
  v9 = -2147024809;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 556;
    v12 = 2147942487LL;
    goto LABEL_15;
  }
LABEL_17:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 558, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180019470  push    rbx
0x180019472  push    rbp
0x180019473  push    rsi
0x180019474  push    rdi
0x180019475  push    r15
0x180019477  sub     rsp, 30h
0x18001947b  mov     rdi, r9
0x18001947e  mov     rsi, r8
0x180019481  mov     rbp, rdx
0x180019484  mov     rbx, rcx
0x180019487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001948e  lea     r15, WPP_GLOBAL_Control
0x180019495  cmp     rcx, r15
0x180019498  jz      short loc_1800194BE
0x18001949a  test    byte ptr [rcx+1Ch], 40h
0x18001949e  jz      short loc_1800194BE
0x1800194a0  cmp     byte ptr [rcx+19h], 6
0x1800194a4  jb      short loc_1800194BE
0x1800194a6  mov     rcx, [rcx+10h]
0x1800194aa  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800194b1  mov     edx, 22Bh
0x1800194b6  mov     r9, rbx
0x1800194b9  call    WPP_SF_q
0x1800194be  mov     rcx, rbx
0x1800194c1  call    ValidateConnectionHandle
0x1800194c6  test    eax, eax
0x1800194c8  jnz     short loc_1800194F5
0x1800194ca  mov     ebx, 80070057h
0x1800194cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194d6  cmp     rcx, r15
0x1800194d9  jz      loc_180019580
0x1800194df  test    byte ptr [rcx+1Ch], 40h
0x1800194e3  jz      short loc_180019557
0x1800194e5  cmp     byte ptr [rcx+19h], 2
0x1800194e9  jb      short loc_180019557
0x1800194eb  mov     edx, 22Ch
0x1800194f0  mov     r9d, ebx
0x1800194f3  jmp     short loc_180019540
0x1800194f5  mov     rax, [rsp+58h+arg_20]
0x1800194fd  mov     edx, 5Fh ; '_'
0x180019502  mov     [rsp+58h+var_30], rsi
0x180019507  mov     r9, rdi
0x18001950a  mov     r8, rbp
0x18001950d  mov     [rsp+58h+var_38], rax
0x180019512  mov     rcx, rbx
0x180019515  call    SubmitRequest
0x18001951a  mov     ebx, eax
0x18001951c  test    eax, eax
0x18001951e  jz      short loc_180019550
0x180019520  mov     rcx, cs:WPP_GLOBAL_Control
0x180019527  cmp     rcx, r15
0x18001952a  jz      short loc_180019580
0x18001952c  test    byte ptr [rcx+1Ch], 40h
0x180019530  jz      short loc_180019557
0x180019532  cmp     byte ptr [rcx+19h], 2
0x180019536  jb      short loc_180019557
0x180019538  mov     edx, 22Dh
0x18001953d  mov     r9d, eax
0x180019540  mov     rcx, [rcx+10h]
0x180019544  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001954b  call    WPP_SF_d
0x180019550  mov     rcx, cs:WPP_GLOBAL_Control
0x180019557  cmp     rcx, r15
0x18001955a  jz      short loc_180019580
0x18001955c  test    byte ptr [rcx+1Ch], 40h
0x180019560  jz      short loc_180019580
0x180019562  cmp     byte ptr [rcx+19h], 6
0x180019566  jb      short loc_180019580
0x180019568  mov     rcx, [rcx+10h]
0x18001956c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180019573  mov     edx, 22Eh
0x180019578  mov     r9d, ebx
0x18001957b  call    WPP_SF_d
0x180019580  mov     eax, ebx
0x180019582  add     rsp, 30h
0x180019586  pop     r15
0x180019588  pop     rdi
0x180019589  pop     rsi
0x18001958a  pop     rbp
0x18001958b  pop     rbx
0x18001958c  retn
```
