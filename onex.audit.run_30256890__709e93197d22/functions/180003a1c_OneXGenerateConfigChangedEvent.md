# OneXGenerateConfigChangedEvent

- ea: `0x180003a1c`
- end: `0x180003c73`
- name: `OneXGenerateConfigChangedEvent`
- size: `599`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180003c80`
- `0x18002a3a0`

## callees

- `0x180003a1c`
- `0x180005440`
- `0x180007f60`
- `0x18000d500`
- `0x180010d40`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x180003bc0`
- `MobileNetworking!SetBufferAndLength` at `0x180003bc0`
- `MobileNetworking!AllocateMemory` at `0x180003abd`
- `MobileNetworking!AllocateMemory` at `0x180003abd`

## string_xrefs

- `0x180003aaa`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall OneXGenerateConfigChangedEvent(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // esi
  _QWORD *v9; // rcx
  unsigned int v10; // ebp
  unsigned int v11; // eax
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v18; // [rsp+80h] [rbp+8h] BYREF

  v4 = *(_DWORD *)(a1 + 20);
  v18 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = *(_DWORD *)(a1 + 20);
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_(v9[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v11 = AllocateMemory(72, &v18, "OneXCreateEvent", 67);
  v12 = v11;
  if ( !v11 )
  {
    *(_DWORD *)(v18 + 16) = 5;
    *(_DWORD *)(v18 + 32) = 2;
    *(_QWORD *)(v18 + 24) = a1;
    goto LABEL_12;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_29:
    OneXDeleteEvent(v18);
    goto LABEL_30;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v10, v11);
LABEL_12:
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v13[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v12);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 68) & 1) != 0 )
      WPP_SF_dd(v13[7], 67, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v4, v12);
    goto LABEL_29;
  }
  *(_DWORD *)(v18 + 40) = 5;
  *(_DWORD *)(v18 + 56) = 2;
  *(_QWORD *)(v18 + 64) = a4;
  v14 = SetBufferAndLength(v18 + 48, v18 + 44, a3, a2);
  v12 = v14;
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_29;
    v16 = 68;
    goto LABEL_28;
  }
  v14 = QueueGlobalEvent(v18);
  v12 = v14;
  if ( v14 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_29;
    v16 = 69;
LABEL_28:
    WPP_SF_dd(v15[7], v16, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v4, v14);
    goto LABEL_29;
  }
LABEL_30:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180003a1c  mov     rax, rsp
0x180003a1f  push    rbx
0x180003a20  push    rbp
0x180003a21  push    rsi
0x180003a22  push    rdi
0x180003a23  push    r12
0x180003a25  push    r13
0x180003a27  push    r14
0x180003a29  push    r15
0x180003a2b  sub     rsp, 38h
0x180003a2f  mov     esi, [rcx+14h]
0x180003a32  mov     r14, r9
0x180003a35  mov     r15, r8
0x180003a38  mov     qword ptr [rax+8], 0
0x180003a40  mov     r12d, edx
0x180003a43  mov     rdi, rcx
0x180003a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a4d  lea     r13, WPP_GLOBAL_Control
0x180003a54  cmp     rcx, r13
0x180003a57  jz      short loc_180003A7E
0x180003a59  test    dword ptr [rcx+44h], 800h
0x180003a60  jz      short loc_180003A7E
0x180003a62  mov     rcx, [rcx+38h]
0x180003a66  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180003a6d  mov     edx, 42h ; 'B'
0x180003a72  call    WPP_SF_
0x180003a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a7e  mov     ebp, [rdi+14h]
0x180003a81  cmp     rcx, r13
0x180003a84  jz      short loc_180003AA4
0x180003a86  test    dword ptr [rcx+44h], 800h
0x180003a8d  jz      short loc_180003AA4
0x180003a8f  mov     rcx, [rcx+38h]
0x180003a93  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180003a9a  mov     edx, 0Ah
0x180003a9f  call    WPP_SF_
0x180003aa4  mov     r9d, 43h ; 'C'
0x180003aaa  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x180003ab1  lea     rdx, [rsp+78h+arg_0]
0x180003ab9  lea     ecx, [r9+5]
0x180003abd  call    cs:__imp_AllocateMemory
0x180003ac3  mov     ebx, eax
0x180003ac5  test    eax, eax
0x180003ac7  jz      short loc_180003AFD
0x180003ac9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ad0  cmp     rcx, r13
0x180003ad3  jz      loc_180003C26
0x180003ad9  test    byte ptr [rcx+44h], 1
0x180003add  jz      short loc_180003B2E
0x180003adf  mov     rcx, [rcx+38h]
0x180003ae3  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180003aea  mov     edx, 0Bh
0x180003aef  mov     [rsp+78h+var_58], eax
0x180003af3  mov     r9d, ebp
0x180003af6  call    WPP_SF_dd
0x180003afb  jmp     short loc_180003B27
0x180003afd  mov     rax, [rsp+78h+arg_0]
0x180003b05  mov     dword ptr [rax+10h], 5
0x180003b0c  mov     rax, [rsp+78h+arg_0]
0x180003b14  mov     dword ptr [rax+20h], 2
0x180003b1b  mov     rax, [rsp+78h+arg_0]
0x180003b23  mov     [rax+18h], rdi
0x180003b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b2e  cmp     rcx, r13
0x180003b31  jz      short loc_180003B5B
0x180003b33  test    dword ptr [rcx+44h], 800h
0x180003b3a  jz      short loc_180003B5B
0x180003b3c  mov     rcx, [rcx+38h]
0x180003b40  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180003b47  mov     edx, 0Ch
0x180003b4c  mov     r9d, ebx
0x180003b4f  call    WPP_SF_D
0x180003b54  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b5b  test    ebx, ebx
0x180003b5d  jz      short loc_180003B80
0x180003b5f  cmp     rcx, r13
0x180003b62  jz      loc_180003C26
0x180003b68  test    byte ptr [rcx+44h], 1
0x180003b6c  jz      loc_180003C26
0x180003b72  mov     edx, 43h ; 'C'
0x180003b77  mov     [rsp+78h+var_58], ebx
0x180003b7b  jmp     loc_180003C13
0x180003b80  mov     rax, [rsp+78h+arg_0]
0x180003b88  mov     r9d, r12d
0x180003b8b  mov     r8, r15
0x180003b8e  mov     dword ptr [rax+28h], 5
0x180003b95  mov     rax, [rsp+78h+arg_0]
0x180003b9d  mov     dword ptr [rax+38h], 2
0x180003ba4  mov     rax, [rsp+78h+arg_0]
0x180003bac  mov     [rax+40h], r14
0x180003bb0  mov     rcx, [rsp+78h+arg_0]
0x180003bb8  lea     rdx, [rcx+2Ch]
0x180003bbc  add     rcx, 30h ; '0'
0x180003bc0  call    cs:__imp_SetBufferAndLength
0x180003bc6  mov     ebx, eax
0x180003bc8  test    eax, eax
0x180003bca  jz      short loc_180003BE5
0x180003bcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bd3  cmp     rcx, r13
0x180003bd6  jz      short loc_180003C26
0x180003bd8  test    byte ptr [rcx+44h], 1
0x180003bdc  jz      short loc_180003C26
0x180003bde  mov     edx, 44h ; 'D'
0x180003be3  jmp     short loc_180003C0F
0x180003be5  mov     rcx, [rsp+78h+arg_0]
0x180003bed  call    QueueGlobalEvent
0x180003bf2  mov     ebx, eax
0x180003bf4  test    eax, eax
0x180003bf6  jz      short loc_180003C33
0x180003bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bff  cmp     rcx, r13
0x180003c02  jz      short loc_180003C26
0x180003c04  test    byte ptr [rcx+44h], 1
0x180003c08  jz      short loc_180003C26
0x180003c0a  mov     edx, 45h ; 'E'
0x180003c0f  mov     [rsp+78h+var_58], eax
0x180003c13  mov     rcx, [rcx+38h]
0x180003c17  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180003c1e  mov     r9d, esi
0x180003c21  call    WPP_SF_dd
0x180003c26  mov     rcx, [rsp+78h+arg_0]
0x180003c2e  call    OneXDeleteEvent
0x180003c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c3a  cmp     rcx, r13
0x180003c3d  jz      short loc_180003C60
0x180003c3f  test    dword ptr [rcx+44h], 800h
0x180003c46  jz      short loc_180003C60
0x180003c48  mov     rcx, [rcx+38h]
0x180003c4c  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180003c53  mov     edx, 46h ; 'F'
0x180003c58  mov     r9d, ebx
0x180003c5b  call    WPP_SF_D
0x180003c60  mov     eax, ebx
0x180003c62  add     rsp, 38h
0x180003c66  pop     r15
0x180003c68  pop     r14
0x180003c6a  pop     r13
0x180003c6c  pop     r12
0x180003c6e  pop     rdi
0x180003c6f  pop     rsi
0x180003c70  pop     rbp
0x180003c71  pop     rbx
0x180003c72  retn
```
