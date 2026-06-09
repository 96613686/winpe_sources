# RxReleaseReadWriteResources

- ea: `0x1400079b0`
- end: `0x140007c99`
- name: `RxReleaseReadWriteResources`
- size: `745`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x140004ac0`
- `0x140008220`
- `0x14000e400`
- `0x140066390`

## callees

- `0x1400079b0`
- `0x140016e20`
- `0x140016e70`
- `0x140017280`
- `0x14001810c`
- `0x14001e3b0`
- `0x140065690`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140007a58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007b86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007a58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140007b86`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140007bf0`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140007bf0`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007b04`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007b51`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007b04`
- `ntoskrnl!ExReleaseResourceForThreadLite` at `0x140007b51`

## pseudocode

```c
void __fastcall RxReleaseReadWriteResources(unsigned __int64 a1, __int64 a2)
{
  ERESOURCE_THREAD v4; // rsi
  unsigned __int8 v5; // bp
  ERESOURCE_THREAD v6; // rsi
  int v7; // ebp

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
  }
  if ( *(_BYTE *)(a1 + 168) )
  {
    v4 = *(_QWORD *)(a1 + 584);
    if ( !v4 )
    {
      v5 = *(_BYTE *)(*(_QWORD *)(a2 + 8) + 26LL) & 0x80;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v5);
      }
      if ( v5 )
      {
        if ( a1 > 0xFFFFFFFFFFFFFFFDuLL )
          goto LABEL_10;
        if ( *(_DWORD *)(*(_QWORD *)(a2 + 304) + 296LL)
          && (*(_DWORD *)(a2 + 156) & 0x80000) == 0
          && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(a1, a2) )
        {
          RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a2);
        }
      }
      else if ( a1 > 0xFFFFFFFFFFFFFFFDuLL )
      {
LABEL_10:
        ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
        goto LABEL_11;
      }
      *(_BYTE *)(a1 + 168) = 0;
      goto LABEL_10;
    }
    v7 = *(_DWORD *)(*(_QWORD *)(a2 + 304) + 296LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, a1, a2, v4);
    }
    if ( v7
      && ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(a2 + 8))
      && (unsigned __int8)RxIsSafeToProcessBufferingStateChange(a1, a2) )
    {
      RxProcessFcbChangeBufferingStateRequestInternal((PVOID)a2);
    }
    *(_BYTE *)(a1 + 168) = 0;
    ExReleaseResourceForThreadLite(*(PERESOURCE *)(a2 + 8), v4);
  }
LABEL_11:
  if ( *(_BYTE *)(a1 + 169) )
  {
    v6 = *(_QWORD *)(a1 + 584);
    if ( v6 )
    {
      *(_BYTE *)(a1 + 169) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v6);
      }
      ExReleaseResourceForThreadLite(*(PERESOURCE *)(a2 + 16), v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids);
      }
      *(_BYTE *)(a1 + 169) = 0;
      ExReleaseResourceLite(*(PERESOURCE *)(a2 + 16));
    }
  }
}

```

## disassembly

```asm
0x1400079b0  mov     [rsp+arg_10], rbx
0x1400079b5  mov     [rsp+arg_18], rdi
0x1400079ba  push    r14
0x1400079bc  sub     rsp, 30h
0x1400079c0  mov     rdi, rdx
0x1400079c3  mov     rbx, rcx
0x1400079c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079cd  lea     r14, WPP_GLOBAL_Control
0x1400079d4  cmp     rcx, r14
0x1400079d7  jz      short loc_1400079E6
0x1400079d9  test    dword ptr [rcx+2Ch], 100h
0x1400079e0  jnz     loc_140007B97
0x1400079e6  cmp     byte ptr [rbx+0A8h], 0
0x1400079ed  mov     [rsp+38h+arg_8], rsi
0x1400079f2  jz      short loc_140007A69
0x1400079f4  mov     rsi, [rbx+248h]
0x1400079fb  mov     [rsp+38h+arg_0], rbp
0x140007a00  test    rsi, rsi
0x140007a03  jnz     loc_140007B15
0x140007a09  mov     rax, [rdi+8]
0x140007a0d  movzx   ecx, byte ptr [rax+1Ah]
0x140007a11  cmp     rbx, 0FFFFFFFFFFFFFFFDh
0x140007a15  jbe     loc_140007AC5
0x140007a1b  mov     sil, 1
0x140007a1e  mov     rax, [rdi+8]
0x140007a22  movzx   ebp, byte ptr [rax+1Ah]
0x140007a26  and     bpl, 80h
0x140007a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a31  cmp     rcx, r14
0x140007a34  jz      short loc_140007A43
0x140007a36  test    dword ptr [rcx+2Ch], 100h
0x140007a3d  jnz     loc_140007C26
0x140007a43  test    bpl, bpl
0x140007a46  jnz     short loc_140007A89
0x140007a48  test    sil, sil
0x140007a4b  jnz     short loc_140007A54
0x140007a4d  mov     byte ptr [rbx+0A8h], 0
0x140007a54  mov     rcx, [rdi+8]; Resource
0x140007a58  call    cs:__imp_ExReleaseResourceLite
0x140007a5f  nop     dword ptr [rax+rax+00h]
0x140007a64  mov     rbp, [rsp+38h+arg_0]
0x140007a69  cmp     byte ptr [rbx+0A9h], 0
0x140007a70  jnz     short loc_140007ACD
0x140007a72  mov     rsi, [rsp+38h+arg_8]
0x140007a77  mov     rbx, [rsp+38h+arg_10]
0x140007a7c  mov     rdi, [rsp+38h+arg_18]
0x140007a81  add     rsp, 30h
0x140007a85  pop     r14
0x140007a87  retn
0x140007a89  test    sil, sil
0x140007a8c  jnz     short loc_140007A54
0x140007a8e  mov     rax, [rdi+130h]
0x140007a95  cmp     dword ptr [rax+128h], 0
0x140007a9c  jz      short loc_140007A4D
0x140007a9e  test    dword ptr [rdi+9Ch], 80000h
0x140007aa8  jnz     short loc_140007A4D
0x140007aaa  mov     rdx, rdi
0x140007aad  mov     rcx, rbx
0x140007ab0  call    RxIsSafeToProcessBufferingStateChange
0x140007ab5  test    al, al
0x140007ab7  jz      short loc_140007A4D
0x140007ab9  xor     edx, edx
0x140007abb  mov     rcx, rdi; Instance
0x140007abe  call    RxProcessFcbChangeBufferingStateRequestInternal
0x140007ac3  jmp     short loc_140007A4D
0x140007ac5  xor     sil, sil
0x140007ac8  jmp     loc_140007A1E
0x140007acd  mov     rsi, [rbx+248h]
0x140007ad4  test    rsi, rsi
0x140007ad7  jz      loc_140007B62
0x140007add  mov     byte ptr [rbx+0A9h], 0
0x140007ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007aeb  cmp     rcx, r14
0x140007aee  jz      short loc_140007AFD
0x140007af0  test    dword ptr [rcx+2Ch], 100h
0x140007af7  jnz     loc_140007C4E
0x140007afd  mov     rcx, [rdi+10h]; Resource
0x140007b01  mov     rdx, rsi; ResourceThreadId
0x140007b04  call    cs:__imp_ExReleaseResourceForThreadLite
0x140007b0b  nop     dword ptr [rax+rax+00h]
0x140007b10  jmp     loc_140007A72
0x140007b15  mov     rax, [rdi+130h]
0x140007b1c  mov     ebp, [rax+128h]
0x140007b22  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b29  cmp     rcx, r14
0x140007b2c  jz      short loc_140007B3B
0x140007b2e  test    dword ptr [rcx+2Ch], 100h
0x140007b35  jnz     loc_140007BBB
0x140007b3b  test    ebp, ebp
0x140007b3d  jnz     loc_140007BEC
0x140007b43  mov     byte ptr [rbx+0A8h], 0
0x140007b4a  mov     rdx, rsi; ResourceThreadId
0x140007b4d  mov     rcx, [rdi+8]; Resource
0x140007b51  call    cs:__imp_ExReleaseResourceForThreadLite
0x140007b58  nop     dword ptr [rax+rax+00h]
0x140007b5d  jmp     loc_140007A64
0x140007b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b69  cmp     rcx, r14
0x140007b6c  jz      short loc_140007B7B
0x140007b6e  test    dword ptr [rcx+2Ch], 100h
0x140007b75  jnz     loc_140007C75
0x140007b7b  mov     byte ptr [rbx+0A9h], 0
0x140007b82  mov     rcx, [rdi+10h]; Resource
0x140007b86  call    cs:__imp_ExReleaseResourceLite
0x140007b8d  nop     dword ptr [rax+rax+00h]
0x140007b92  jmp     loc_140007A72
0x140007b97  cmp     byte ptr [rcx+29h], 4
0x140007b9b  jb      loc_1400079E6
0x140007ba1  mov     rcx, [rcx+18h]
0x140007ba5  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140007bac  mov     edx, 0Fh
0x140007bb1  call    WPP_SF_
0x140007bb6  jmp     loc_1400079E6
0x140007bbb  cmp     byte ptr [rcx+29h], 4
0x140007bbf  jb      loc_140007B3B
0x140007bc5  mov     rcx, [rcx+18h]
0x140007bc9  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140007bd0  mov     edx, 0Eh
0x140007bd5  mov     [rsp+38h+var_10], rsi
0x140007bda  mov     r9, rbx
0x140007bdd  mov     [rsp+38h+var_18], rdi
0x140007be2  call    WPP_SF_qqq
0x140007be7  jmp     loc_140007B3B
0x140007bec  mov     rcx, [rdi+8]; Resource
0x140007bf0  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140007bf7  nop     dword ptr [rax+rax+00h]
0x140007bfc  test    al, al
0x140007bfe  jz      loc_140007B43
0x140007c04  mov     rdx, rdi
0x140007c07  mov     rcx, rbx
0x140007c0a  call    RxIsSafeToProcessBufferingStateChange
0x140007c0f  test    al, al
0x140007c11  jz      loc_140007B43
0x140007c17  xor     edx, edx
0x140007c19  mov     rcx, rdi; Instance
0x140007c1c  call    RxProcessFcbChangeBufferingStateRequestInternal
0x140007c21  jmp     loc_140007B43
0x140007c26  cmp     byte ptr [rcx+29h], 4
0x140007c2a  jb      loc_140007A43
0x140007c30  mov     rcx, [rcx+18h]
0x140007c34  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140007c3b  movzx   r9d, bpl
0x140007c3f  mov     edx, 0Dh
0x140007c44  call    WPP_SF_d
0x140007c49  jmp     loc_140007A43
0x140007c4e  cmp     byte ptr [rcx+29h], 4
0x140007c52  jb      loc_140007AFD
0x140007c58  mov     rcx, [rcx+18h]
0x140007c5c  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140007c63  mov     edx, 15h
0x140007c68  mov     r9, rsi
0x140007c6b  call    WPP_SF_q
0x140007c70  jmp     loc_140007AFD
0x140007c75  cmp     byte ptr [rcx+29h], 4
0x140007c79  jb      loc_140007B7B
0x140007c7f  mov     rcx, [rcx+18h]
0x140007c83  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140007c8a  mov     edx, 14h
0x140007c8f  call    WPP_SF_
0x140007c94  jmp     loc_140007B7B
```
