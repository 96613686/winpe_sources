# RxCommonDevFCBClose

- ea: `0x140048a00`
- end: `0x140048c99`
- name: `RxCommonDevFCBClose`
- size: `665`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000ce10`
- `0x14000f130`
- `0x140015230`
- `0x140016e70`
- `0x140025d00`
- `0x140048a00`
- `0x140058f00`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048bc6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048bc6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c45`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c6b`
- `MUP!MupUnpinKnownPrefix` at `0x140048b3b`
- `MUP!MupUnpinKnownPrefix` at `0x140048b3b`

## pseudocode

```c
__int64 __fastcall RxCommonDevFCBClose(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  _WORD *v3; // rbx
  __int64 v5; // rdi
  __int64 v6; // rax
  __int16 v7; // bp
  LOCK_HOLDING_STATE v8; // r15d
  __int64 v10; // rax
  unsigned int v11; // ebp
  _BYTE *v12; // r12
  int v13; // edi
  _QWORD *v14; // r13
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 (__fastcall *v19)(_QWORD *, __int64 *); // rax
  int v20; // eax
  __int64 v21; // rsi
  __int64 v22; // [rsp+70h] [rbp+8h] BYREF
  PVOID P; // [rsp+78h] [rbp+10h] BYREF
  __int64 v24; // [rsp+80h] [rbp+18h]

  v2 = *(_QWORD *)(a2 + 184);
  v3 = *(_WORD **)(a1 + 72);
  P = 0;
  v5 = *(_QWORD *)(v2 + 48);
  v6 = *(_QWORD *)(a1 + 80);
  v22 = 0;
  v24 = *(_QWORD *)(v6 + 504);
  v7 = RxDecodeFileObject2(v5, &v22, &P);
  v8 = LHS_ExclusiveLockHeld;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_5e986c1920953da49ef62636cf2f6d90_Traceguids, a1, v5);
  }
  if ( v7 != -5085 && v7 != -5080 )
    return 3221225488LL;
  *(_QWORD *)(v5 + 24) = -1;
  *(_QWORD *)(v5 + 40) = 0;
  if ( v3 )
  {
    if ( *v3 == 0xEB1C )
    {
      v10 = *((_QWORD *)v3 + 5);
      v11 = 0;
      v12 = P;
      if ( v10 )
      {
        LODWORD(v22) = 10;
        v13 = -1073741823;
        _InterlockedDecrement((volatile signed __int32 *)(v10 + 60));
        v14 = (_QWORD *)*((_QWORD *)v3 + 5);
        if ( v12[152] )
        {
          v15 = v14[4];
          v16 = *(_QWORD *)(*(_QWORD *)(v15 + 32) + 88LL);
          if ( v16 )
            v17 = *(_QWORD *)(v16 + 40);
          else
            v17 = 0;
          MupUnpinKnownPrefix(*(_QWORD *)(v15 + 88), v17);
          v12[152] = 0;
        }
        v18 = *(_QWORD *)(a1 + 888);
        if ( v18 )
        {
          v19 = *(__int64 (__fastcall **)(_QWORD *, __int64 *))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v14[4] + 32LL) + 48LL)
                                                                          + 352LL)
                                                              + 584LL);
          if ( v19 )
          {
            v20 = v19(v14, &v22);
            v18 = *(_QWORD *)(a1 + 888);
            v13 = v20;
          }
          else
          {
            v13 = -1073741822;
          }
          if ( *(_DWORD *)(a1 + 872) != 3 )
            __int2c();
          RfsReleaseRundownProtection(v18);
          *(_QWORD *)(a1 + 888) = 0;
          *(_DWORD *)(a1 + 872) = 0;
        }
        v21 = v24;
        ExAcquireResourceExclusiveLite((PERESOURCE)(v24 + 24), 1u);
        if ( v13 < 0 || (_DWORD)v22 )
        {
          v8 = LHS_LockNotHeld;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, &WPP_5e986c1920953da49ef62636cf2f6d90_Traceguids, v14);
        }
        RxDereference(v14, v8);
        ExReleaseResourceLite((PERESOURCE)(v21 + 24));
      }
      if ( (*((_DWORD *)v3 + 18) & 0x80000) != 0 )
      {
        ExFreePoolWithTag(*((PVOID *)v3 + 10), 0);
        *((_QWORD *)v3 + 10) = 0;
      }
      ExFreePoolWithTag(v3, 0);
      ExFreePoolWithTag(v12, 0);
    }
    else
    {
      return (unsigned int)-1073741822;
    }
    return v11;
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)(v22 + 192));
    return 0;
  }
}

```

## disassembly

```asm
0x140048a00  mov     r11, rsp
0x140048a03  mov     [r11+20h], rbx
0x140048a07  push    rbp
0x140048a08  push    rsi
0x140048a09  push    rdi
0x140048a0a  push    r12
0x140048a0c  push    r13
0x140048a0e  push    r14
0x140048a10  push    r15
0x140048a12  sub     rsp, 30h
0x140048a16  mov     rax, [rdx+0B8h]
0x140048a1d  lea     r8, [r11+10h]
0x140048a21  mov     rbx, [rcx+48h]
0x140048a25  lea     rdx, [r11+8]
0x140048a29  xor     r14d, r14d
0x140048a2c  mov     rsi, rcx
0x140048a2f  mov     [r11+10h], r14
0x140048a33  mov     rdi, [rax+30h]
0x140048a37  mov     rax, [rcx+50h]
0x140048a3b  mov     rcx, rdi
0x140048a3e  mov     [r11+8], r14
0x140048a42  mov     rax, [rax+1F8h]
0x140048a49  mov     [rsp+68h+arg_10], rax
0x140048a51  call    RxDecodeFileObject2
0x140048a56  movzx   ebp, ax
0x140048a59  mov     rcx, cs:WPP_GLOBAL_Control
0x140048a60  lea     rax, WPP_GLOBAL_Control
0x140048a67  lea     r13d, [r14+0Ah]
0x140048a6b  lea     r15d, [r14+2]
0x140048a6f  cmp     rcx, rax
0x140048a72  jz      short loc_140048A9D
0x140048a74  mov     edx, [rcx+2Ch]
0x140048a77  test    r15b, dl
0x140048a7a  jz      short loc_140048A9D
0x140048a7c  cmp     byte ptr [rcx+29h], 4
0x140048a80  jb      short loc_140048A9D
0x140048a82  mov     rcx, [rcx+18h]
0x140048a86  lea     r8, WPP_5e986c1920953da49ef62636cf2f6d90_Traceguids
0x140048a8d  mov     edx, r13d
0x140048a90  mov     [rsp+68h+var_48], rdi
0x140048a95  mov     r9, rsi
0x140048a98  call    WPP_SF_qq
0x140048a9d  mov     eax, 0EC23h
0x140048aa2  cmp     bp, ax
0x140048aa5  jz      short loc_140048ABB
0x140048aa7  mov     eax, 0EC28h
0x140048aac  cmp     bp, ax
0x140048aaf  jz      short loc_140048ABB
0x140048ab1  mov     eax, 0C0000010h
0x140048ab6  jmp     loc_140048C80
0x140048abb  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x140048ac3  mov     [rdi+28h], r14
0x140048ac7  test    rbx, rbx
0x140048aca  jnz     short loc_140048ADF
0x140048acc  mov     rax, [rsp+68h+arg_0]
0x140048ad1  lock dec dword ptr [rax+0C0h]
0x140048ad8  xor     eax, eax
0x140048ada  jmp     loc_140048C80
0x140048adf  mov     eax, 0EB1Ch
0x140048ae4  cmp     [rbx], ax
0x140048ae7  jnz     loc_140048C79
0x140048aed  mov     rax, [rbx+28h]
0x140048af1  mov     ebp, r14d
0x140048af4  mov     r12, [rsp+68h+P]
0x140048af9  test    rax, rax
0x140048afc  jz      loc_140048C36
0x140048b02  mov     dword ptr [rsp+68h+arg_0], r13d
0x140048b07  mov     edi, 0C0000001h
0x140048b0c  lock dec dword ptr [rax+3Ch]
0x140048b10  mov     r13, [rbx+28h]
0x140048b14  cmp     [r12+98h], bpl
0x140048b1c  jz      short loc_140048B4F
0x140048b1e  mov     r8, [r13+20h]
0x140048b22  mov     rax, [r8+20h]
0x140048b26  mov     rcx, [rax+58h]
0x140048b2a  test    rcx, rcx
0x140048b2d  jz      short loc_140048B35
0x140048b2f  mov     rdx, [rcx+28h]
0x140048b33  jmp     short loc_140048B37
0x140048b35  xor     edx, edx
0x140048b37  mov     rcx, [r8+58h]
0x140048b3b  call    cs:__imp_MupUnpinKnownPrefix
0x140048b42  nop     dword ptr [rax+rax+00h]
0x140048b47  mov     [r12+98h], bpl
0x140048b4f  mov     rdx, [rsi+378h]
0x140048b56  test    rdx, rdx
0x140048b59  jz      short loc_140048BB8
0x140048b5b  mov     rax, [r13+20h]
0x140048b5f  mov     rcx, [rax+20h]
0x140048b63  mov     rax, [rcx+30h]
0x140048b67  mov     rcx, [rax+160h]
0x140048b6e  mov     rax, [rcx+248h]
0x140048b75  test    rax, rax
0x140048b78  jnz     short loc_140048B81
0x140048b7a  mov     edi, 0C0000002h
0x140048b7f  jmp     short loc_140048B97
0x140048b81  lea     rdx, [rsp+68h+arg_0]
0x140048b86  mov     rcx, r13
0x140048b89  call    _guard_dispatch_icall
0x140048b8e  mov     rdx, [rsi+378h]
0x140048b95  mov     edi, eax
0x140048b97  cmp     dword ptr [rsi+368h], 3
0x140048b9e  jz      short loc_140048BA2
0x140048ba0  int     2Ch; Windows NT - assertion failure
0x140048ba2  mov     rcx, rdx
0x140048ba5  call    RfsReleaseRundownProtection
0x140048baa  mov     [rsi+378h], r14
0x140048bb1  mov     [rsi+368h], r14d
0x140048bb8  mov     rsi, [rsp+68h+arg_10]
0x140048bc0  mov     dl, 1; Wait
0x140048bc2  lea     rcx, [rsi+18h]; Resource
0x140048bc6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140048bcd  nop     dword ptr [rax+rax+00h]
0x140048bd2  test    edi, edi
0x140048bd4  js      short loc_140048C18
0x140048bd6  cmp     dword ptr [rsp+68h+arg_0], r14d
0x140048bdb  jnz     short loc_140048C18
0x140048bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140048be4  lea     rax, WPP_GLOBAL_Control
0x140048beb  cmp     rcx, rax
0x140048bee  jz      short loc_140048C1B
0x140048bf0  mov     eax, [rcx+2Ch]
0x140048bf3  test    r15b, al
0x140048bf6  jz      short loc_140048C1B
0x140048bf8  cmp     byte ptr [rcx+29h], 4
0x140048bfc  jb      short loc_140048C1B
0x140048bfe  mov     rcx, [rcx+18h]
0x140048c02  lea     r8, WPP_5e986c1920953da49ef62636cf2f6d90_Traceguids
0x140048c09  mov     edx, 0Bh
0x140048c0e  mov     r9, r13
0x140048c11  call    WPP_SF_q
0x140048c16  jmp     short loc_140048C1B
0x140048c18  mov     r15d, r14d
0x140048c1b  mov     edx, r15d; LockHoldingState
0x140048c1e  mov     rcx, r13; Instance
0x140048c21  call    RxDereference
0x140048c26  lea     rcx, [rsi+18h]; Resource
0x140048c2a  call    cs:__imp_ExReleaseResourceLite
0x140048c31  nop     dword ptr [rax+rax+00h]
0x140048c36  test    dword ptr [rbx+48h], 80000h
0x140048c3d  jz      short loc_140048C55
0x140048c3f  mov     rcx, [rbx+50h]; P
0x140048c43  xor     edx, edx; Tag
0x140048c45  call    cs:__imp_ExFreePoolWithTag
0x140048c4c  nop     dword ptr [rax+rax+00h]
0x140048c51  mov     [rbx+50h], r14
0x140048c55  xor     edx, edx; Tag
0x140048c57  mov     rcx, rbx; P
0x140048c5a  call    cs:__imp_ExFreePoolWithTag
0x140048c61  nop     dword ptr [rax+rax+00h]
0x140048c66  xor     edx, edx; Tag
0x140048c68  mov     rcx, r12; P
0x140048c6b  call    cs:__imp_ExFreePoolWithTag
0x140048c72  nop     dword ptr [rax+rax+00h]
0x140048c77  jmp     short loc_140048C7E
0x140048c79  mov     ebp, 0C0000002h
0x140048c7e  mov     eax, ebp
0x140048c80  mov     rbx, [rsp+68h+arg_18]
0x140048c88  add     rsp, 30h
0x140048c8c  pop     r15
0x140048c8e  pop     r14
0x140048c90  pop     r13
0x140048c92  pop     r12
0x140048c94  pop     rdi
0x140048c95  pop     rsi
0x140048c96  pop     rbp
0x140048c97  retn
```
