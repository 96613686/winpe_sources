# RasSetDevConfig

- ea: `0x18001fa50`
- end: `0x18001fb93`
- name: `RasSetDevConfig`
- size: `323`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001fa50`
- `0x180021b14`
- `0x180022320`

## pseudocode

```c
__int64 __fastcall RasSetDevConfig(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v13; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 481, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a4);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 482, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 601);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
      {
        v10 = 483;
LABEL_24:
        WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
        return v9;
      }
    }
    return v9;
  }
  LODWORD(v13) = a4;
  v11 = SubmitLocalRequest(0x48u, a1, a2, a3, v13);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_20;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 484, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 485;
    goto LABEL_24;
  }
  return v9;
}

```

## disassembly

```asm
0x18001fa50  push    rbx
0x18001fa52  push    rbp
0x18001fa53  push    rsi
0x18001fa54  push    rdi
0x18001fa55  push    r12
0x18001fa57  push    r15
0x18001fa59  sub     rsp, 38h
0x18001fa5d  mov     edi, r9d
0x18001fa60  mov     rsi, r8
0x18001fa63  mov     rbp, rdx
0x18001fa66  mov     rbx, rcx
0x18001fa69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa70  lea     r15, WPP_GLOBAL_Control
0x18001fa77  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001fa7e  cmp     rcx, r15
0x18001fa81  jz      short loc_18001FAA8
0x18001fa83  test    byte ptr [rcx+1Ch], 40h
0x18001fa87  jz      short loc_18001FAA8
0x18001fa89  cmp     byte ptr [rcx+19h], 6
0x18001fa8d  jb      short loc_18001FAA8
0x18001fa8f  mov     rcx, [rcx+10h]
0x18001fa93  mov     edx, 1E1h
0x18001fa98  mov     dword ptr [rsp+68h+var_48], r9d
0x18001fa9d  mov     r8, r12
0x18001faa0  mov     r9, rbx
0x18001faa3  call    WPP_SF_qd
0x18001faa8  mov     rcx, rbx
0x18001faab  call    ValidatePortHandle
0x18001fab0  test    eax, eax
0x18001fab2  jnz     short loc_18001FB0E
0x18001fab4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fabb  mov     ebx, 259h
0x18001fac0  cmp     rcx, r15
0x18001fac3  jz      loc_18001FB83
0x18001fac9  test    byte ptr [rcx+1Ch], 40h
0x18001facd  jz      short loc_18001FAEE
0x18001facf  cmp     byte ptr [rcx+19h], 2
0x18001fad3  jb      short loc_18001FAEE
0x18001fad5  mov     rcx, [rcx+10h]
0x18001fad9  lea     edx, [rbx-77h]
0x18001fadc  mov     r9d, ebx
0x18001fadf  mov     r8, r12
0x18001fae2  call    WPP_SF_d
0x18001fae7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faee  cmp     rcx, r15
0x18001faf1  jz      loc_18001FB83
0x18001faf7  test    byte ptr [rcx+1Ch], 40h
0x18001fafb  jz      loc_18001FB83
0x18001fb01  cmp     byte ptr [rcx+19h], 6
0x18001fb05  jb      short loc_18001FB83
0x18001fb07  mov     edx, 1E3h
0x18001fb0c  jmp     short loc_18001FB74
0x18001fb0e  mov     ecx, 48h ; 'H'
0x18001fb13  mov     dword ptr [rsp+68h+var_48], edi
0x18001fb17  mov     r9, rsi
0x18001fb1a  mov     r8, rbp
0x18001fb1d  mov     rdx, rbx
0x18001fb20  call    SubmitLocalRequest
0x18001fb25  mov     ebx, eax
0x18001fb27  test    eax, eax
0x18001fb29  jz      short loc_18001FB57
0x18001fb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb32  cmp     rcx, r15
0x18001fb35  jz      short loc_18001FB83
0x18001fb37  test    byte ptr [rcx+1Ch], 40h
0x18001fb3b  jz      short loc_18001FB5E
0x18001fb3d  cmp     byte ptr [rcx+19h], 2
0x18001fb41  jb      short loc_18001FB5E
0x18001fb43  mov     rcx, [rcx+10h]
0x18001fb47  mov     edx, 1E4h
0x18001fb4c  mov     r9d, eax
0x18001fb4f  mov     r8, r12
0x18001fb52  call    WPP_SF_d
0x18001fb57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb5e  cmp     rcx, r15
0x18001fb61  jz      short loc_18001FB83
0x18001fb63  test    byte ptr [rcx+1Ch], 40h
0x18001fb67  jz      short loc_18001FB83
0x18001fb69  cmp     byte ptr [rcx+19h], 6
0x18001fb6d  jb      short loc_18001FB83
0x18001fb6f  mov     edx, 1E5h
0x18001fb74  mov     rcx, [rcx+10h]
0x18001fb78  mov     r9d, ebx
0x18001fb7b  mov     r8, r12
0x18001fb7e  call    WPP_SF_d
0x18001fb83  mov     eax, ebx
0x18001fb85  add     rsp, 38h
0x18001fb89  pop     r15
0x18001fb8b  pop     r12
0x18001fb8d  pop     rdi
0x18001fb8e  pop     rsi
0x18001fb8f  pop     rbp
0x18001fb90  pop     rbx
0x18001fb91  retn
```
