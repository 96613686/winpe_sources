# RasPortSetProtocolCompression

- ea: `0x18001c590`
- end: `0x18001c6a8`
- name: `RasPortSetProtocolCompression`
- size: `280`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001c590`
- `0x180021000`
- `0x1800217a0`

## pseudocode

```c
__int64 __fastcall RasPortSetProtocolCompression(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 320, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 321;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x2Bu, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 323;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001c590  push    rbx
0x18001c592  push    rbp
0x18001c593  push    rsi
0x18001c594  push    rdi
0x18001c595  push    r15
0x18001c597  sub     rsp, 30h
0x18001c59b  mov     rsi, r9
0x18001c59e  mov     rbp, r8
0x18001c5a1  mov     edi, edx
0x18001c5a3  mov     rbx, rcx
0x18001c5a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5ad  lea     r15, WPP_GLOBAL_Control
0x18001c5b4  cmp     rcx, r15
0x18001c5b7  jz      short loc_18001C5E1
0x18001c5b9  test    byte ptr [rcx+1Ch], 40h
0x18001c5bd  jz      short loc_18001C5E1
0x18001c5bf  cmp     byte ptr [rcx+19h], 6
0x18001c5c3  jb      short loc_18001C5E1
0x18001c5c5  mov     rcx, [rcx+10h]
0x18001c5c9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c5d0  mov     edx, 140h
0x18001c5d5  mov     dword ptr [rsp+58h+var_38], edi
0x18001c5d9  mov     r9, rbx
0x18001c5dc  call    WPP_SF_qd
0x18001c5e1  mov     rcx, rbx
0x18001c5e4  call    ValidatePortHandle
0x18001c5e9  test    eax, eax
0x18001c5eb  jnz     short loc_18001C61D
0x18001c5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5f4  mov     ebx, 259h
0x18001c5f9  cmp     rcx, r15
0x18001c5fc  jz      loc_18001C69B
0x18001c602  test    byte ptr [rcx+1Ch], 40h
0x18001c606  jz      loc_18001C69B
0x18001c60c  cmp     byte ptr [rcx+19h], 2
0x18001c610  jb      loc_18001C69B
0x18001c616  mov     edx, 141h
0x18001c61b  jmp     short loc_18001C688
0x18001c61d  mov     ecx, 2Bh ; '+'
0x18001c622  mov     [rsp+58h+var_38], rsi
0x18001c627  mov     r9, rbp
0x18001c62a  mov     r8d, edi
0x18001c62d  mov     rdx, rbx
0x18001c630  call    SubmitLocalRequest
0x18001c635  mov     ebx, eax
0x18001c637  test    eax, eax
0x18001c639  jz      short loc_18001C66B
0x18001c63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c642  cmp     rcx, r15
0x18001c645  jz      short loc_18001C69B
0x18001c647  test    byte ptr [rcx+1Ch], 40h
0x18001c64b  jz      short loc_18001C672
0x18001c64d  cmp     byte ptr [rcx+19h], 2
0x18001c651  jb      short loc_18001C672
0x18001c653  mov     rcx, [rcx+10h]
0x18001c657  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c65e  mov     edx, 142h
0x18001c663  mov     r9d, eax
0x18001c666  call    WPP_SF_d
0x18001c66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c672  cmp     rcx, r15
0x18001c675  jz      short loc_18001C69B
0x18001c677  test    byte ptr [rcx+1Ch], 40h
0x18001c67b  jz      short loc_18001C69B
0x18001c67d  cmp     byte ptr [rcx+19h], 6
0x18001c681  jb      short loc_18001C69B
0x18001c683  mov     edx, 143h
0x18001c688  mov     rcx, [rcx+10h]
0x18001c68c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001c693  mov     r9d, ebx
0x18001c696  call    WPP_SF_d
0x18001c69b  mov     eax, ebx
0x18001c69d  add     rsp, 30h
0x18001c6a1  pop     r15
0x18001c6a3  pop     rdi
0x18001c6a4  pop     rsi
0x18001c6a5  pop     rbp
0x18001c6a6  pop     rbx
0x18001c6a7  retn
```
