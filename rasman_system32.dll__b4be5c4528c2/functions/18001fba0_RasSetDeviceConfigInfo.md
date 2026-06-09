# RasSetDeviceConfigInfo

- ea: `0x18001fba0`
- end: `0x18001fcad`
- name: `RasSetDeviceConfigInfo`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180011f80`
- `0x180012330`
- `0x18001fba0`
- `0x180021ae4`
- `0x180021b14`

## pseudocode

```c
__int64 __fastcall RasSetDeviceConfigInfo(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 551, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  if ( (unsigned int)ValidateConnectionHandle(a1) )
  {
    v12 = SubmitRequest(a1, 0x5Eu, a2, a3, a4);
    v8 = v12;
    if ( !v12 )
    {
LABEL_16:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v10 = 553;
    v11 = v12;
LABEL_15:
    WPP_SF_d(v9[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
    goto LABEL_16;
  }
  v8 = -2147024809;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 552;
    v11 = 2147942487LL;
    goto LABEL_15;
  }
LABEL_17:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 554, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001fba0  push    rbx
0x18001fba2  push    rbp
0x18001fba3  push    rsi
0x18001fba4  push    rdi
0x18001fba5  push    r15
0x18001fba7  sub     rsp, 30h
0x18001fbab  mov     rdi, r9
0x18001fbae  mov     esi, r8d
0x18001fbb1  mov     ebp, edx
0x18001fbb3  mov     rbx, rcx
0x18001fbb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbbd  lea     r15, WPP_GLOBAL_Control
0x18001fbc4  cmp     rcx, r15
0x18001fbc7  jz      short loc_18001FBEA
0x18001fbc9  test    byte ptr [rcx+1Ch], 40h
0x18001fbcd  jz      short loc_18001FBEA
0x18001fbcf  cmp     byte ptr [rcx+19h], 6
0x18001fbd3  jb      short loc_18001FBEA
0x18001fbd5  mov     rcx, [rcx+10h]
0x18001fbd9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001fbe0  mov     edx, 227h
0x18001fbe5  call    WPP_SF_
0x18001fbea  mov     rcx, rbx
0x18001fbed  call    ValidateConnectionHandle
0x18001fbf2  test    eax, eax
0x18001fbf4  jnz     short loc_18001FC21
0x18001fbf6  mov     ebx, 80070057h
0x18001fbfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc02  cmp     rcx, r15
0x18001fc05  jz      loc_18001FC9F
0x18001fc0b  test    byte ptr [rcx+1Ch], 40h
0x18001fc0f  jz      short loc_18001FC76
0x18001fc11  cmp     byte ptr [rcx+19h], 2
0x18001fc15  jb      short loc_18001FC76
0x18001fc17  mov     edx, 228h
0x18001fc1c  mov     r9d, ebx
0x18001fc1f  jmp     short loc_18001FC5F
0x18001fc21  mov     edx, 5Eh ; '^'
0x18001fc26  mov     [rsp+58h+var_38], rdi
0x18001fc2b  mov     r9d, esi
0x18001fc2e  mov     r8d, ebp
0x18001fc31  mov     rcx, rbx
0x18001fc34  call    SubmitRequest
0x18001fc39  mov     ebx, eax
0x18001fc3b  test    eax, eax
0x18001fc3d  jz      short loc_18001FC6F
0x18001fc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc46  cmp     rcx, r15
0x18001fc49  jz      short loc_18001FC9F
0x18001fc4b  test    byte ptr [rcx+1Ch], 40h
0x18001fc4f  jz      short loc_18001FC76
0x18001fc51  cmp     byte ptr [rcx+19h], 2
0x18001fc55  jb      short loc_18001FC76
0x18001fc57  mov     edx, 229h
0x18001fc5c  mov     r9d, eax
0x18001fc5f  mov     rcx, [rcx+10h]
0x18001fc63  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001fc6a  call    WPP_SF_d
0x18001fc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc76  cmp     rcx, r15
0x18001fc79  jz      short loc_18001FC9F
0x18001fc7b  test    byte ptr [rcx+1Ch], 40h
0x18001fc7f  jz      short loc_18001FC9F
0x18001fc81  cmp     byte ptr [rcx+19h], 6
0x18001fc85  jb      short loc_18001FC9F
0x18001fc87  mov     rcx, [rcx+10h]
0x18001fc8b  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001fc92  mov     edx, 22Ah
0x18001fc97  mov     r9d, ebx
0x18001fc9a  call    WPP_SF_d
0x18001fc9f  mov     eax, ebx
0x18001fca1  add     rsp, 30h
0x18001fca5  pop     r15
0x18001fca7  pop     rdi
0x18001fca8  pop     rsi
0x18001fca9  pop     rbp
0x18001fcaa  pop     rbx
0x18001fcab  retn
```
