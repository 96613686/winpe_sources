# RasPortGetProtocolCompression

- ea: `0x18001bc80`
- end: `0x18001bd99`
- name: `RasPortGetProtocolCompression`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800030d0`
- `0x1800121b4`
- `0x18001bc80`
- `0x180021b14`
- `0x180022320`

## pseudocode

```c
__int64 __fastcall RasPortGetProtocolCompression(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 317;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x2Au, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 319;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001bc80  push    rbx
0x18001bc82  push    rbp
0x18001bc83  push    rsi
0x18001bc84  push    rdi
0x18001bc85  push    r15
0x18001bc87  sub     rsp, 30h
0x18001bc8b  mov     rsi, r9
0x18001bc8e  mov     rbp, r8
0x18001bc91  mov     edi, edx
0x18001bc93  mov     rbx, rcx
0x18001bc96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc9d  lea     r15, WPP_GLOBAL_Control
0x18001bca4  cmp     rcx, r15
0x18001bca7  jz      short loc_18001BCD1
0x18001bca9  test    byte ptr [rcx+1Ch], 40h
0x18001bcad  jz      short loc_18001BCD1
0x18001bcaf  cmp     byte ptr [rcx+19h], 6
0x18001bcb3  jb      short loc_18001BCD1
0x18001bcb5  mov     rcx, [rcx+10h]
0x18001bcb9  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bcc0  mov     edx, 13Ch
0x18001bcc5  mov     dword ptr [rsp+58h+var_38], edi
0x18001bcc9  mov     r9, rbx
0x18001bccc  call    WPP_SF_qd
0x18001bcd1  mov     rcx, rbx
0x18001bcd4  call    ValidatePortHandle
0x18001bcd9  test    eax, eax
0x18001bcdb  jnz     short loc_18001BD0D
0x18001bcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bce4  mov     ebx, 259h
0x18001bce9  cmp     rcx, r15
0x18001bcec  jz      loc_18001BD8B
0x18001bcf2  test    byte ptr [rcx+1Ch], 40h
0x18001bcf6  jz      loc_18001BD8B
0x18001bcfc  cmp     byte ptr [rcx+19h], 2
0x18001bd00  jb      loc_18001BD8B
0x18001bd06  mov     edx, 13Dh
0x18001bd0b  jmp     short loc_18001BD78
0x18001bd0d  mov     ecx, 2Ah ; '*'
0x18001bd12  mov     [rsp+58h+var_38], rsi
0x18001bd17  mov     r9, rbp
0x18001bd1a  mov     r8d, edi
0x18001bd1d  mov     rdx, rbx
0x18001bd20  call    SubmitLocalRequest
0x18001bd25  mov     ebx, eax
0x18001bd27  test    eax, eax
0x18001bd29  jz      short loc_18001BD5B
0x18001bd2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd32  cmp     rcx, r15
0x18001bd35  jz      short loc_18001BD8B
0x18001bd37  test    byte ptr [rcx+1Ch], 40h
0x18001bd3b  jz      short loc_18001BD62
0x18001bd3d  cmp     byte ptr [rcx+19h], 2
0x18001bd41  jb      short loc_18001BD62
0x18001bd43  mov     rcx, [rcx+10h]
0x18001bd47  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bd4e  mov     edx, 13Eh
0x18001bd53  mov     r9d, eax
0x18001bd56  call    WPP_SF_d
0x18001bd5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd62  cmp     rcx, r15
0x18001bd65  jz      short loc_18001BD8B
0x18001bd67  test    byte ptr [rcx+1Ch], 40h
0x18001bd6b  jz      short loc_18001BD8B
0x18001bd6d  cmp     byte ptr [rcx+19h], 6
0x18001bd71  jb      short loc_18001BD8B
0x18001bd73  mov     edx, 13Fh
0x18001bd78  mov     rcx, [rcx+10h]
0x18001bd7c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001bd83  mov     r9d, ebx
0x18001bd86  call    WPP_SF_d
0x18001bd8b  mov     eax, ebx
0x18001bd8d  add     rsp, 30h
0x18001bd91  pop     r15
0x18001bd93  pop     rdi
0x18001bd94  pop     rsi
0x18001bd95  pop     rbp
0x18001bd96  pop     rbx
0x18001bd97  retn
```
