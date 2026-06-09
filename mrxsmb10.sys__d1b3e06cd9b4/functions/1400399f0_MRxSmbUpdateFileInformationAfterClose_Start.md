# MRxSmbUpdateFileInformationAfterClose_Start

- ea: `0x1400399f0`
- end: `0x140039b95`
- name: `MRxSmbUpdateFileInformationAfterClose_Start`
- size: `421`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x14000dc44`
- `0x140010358`
- `0x1400108c0`
- `0x14002ea60`
- `0x1400399f0`
- `0x140046a50`

## pseudocode

```c
__int64 __fastcall MRxSmbUpdateFileInformationAfterClose_Start(char *pContext, __int64 a2)
{
  char *v2; // r15
  unsigned int v5; // ebp
  unsigned __int16 *v6; // rdi
  int v7; // edi
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  int v12; // [rsp+30h] [rbp-58h]
  int v13; // [rsp+38h] [rbp-50h]

  v2 = pContext + 888;
  v5 = -1073741670;
  v6 = (unsigned __int16 *)(*(_QWORD *)(a2 + 56) + 360LL);
  if ( *(_QWORD *)(a2 + 56) == -360 )
    v6 = (unsigned __int16 *)*((_QWORD *)pContext + 108);
  else
    *((_QWORD *)pContext + 108) = v6;
  MRxSmbSetInitialSMB(pContext + 888);
  v7 = *v6 + 14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      96,
      WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      a2,
      ((v7 + 3) & 0xFFFFFFFC) + 64,
      v7);
  if ( ((v7 + 3) & 0xFFFFFFFC) + 64 <= *((_DWORD *)pContext + 92) )
  {
    v5 = _MRxSmbSimpleSyncTransact2(pContext, *((_QWORD *)v2 + 3), v7, v12, v13, (__int64)MRxSmbFixupFindFirst);
    if ( !v5 )
    {
      v8 = *((_QWORD *)v2 + 4);
      v9 = *(_QWORD *)(a2 + 456);
      v10 = *(unsigned __int16 *)(v8 + 47);
      *(_QWORD *)v9 = *(_QWORD *)(v10 + v8 + 8);
      *(_QWORD *)(v9 + 8) = *(_QWORD *)(v10 + v8 + 16);
      *(_QWORD *)(v9 + 16) = *(_QWORD *)(v10 + v8 + 24);
      *(_QWORD *)(v9 + 24) = *(_QWORD *)(v10 + v8 + 32);
      *(_DWORD *)(v9 + 48) = *(_DWORD *)(v10 + v8 + 56);
      *(_QWORD *)(v9 + 40) = *(_QWORD *)(v10 + v8 + 40);
      *(_QWORD *)(v9 + 32) = *(_QWORD *)(v10 + v8 + 48);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        WPP_SF_qDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          v8,
          *(_QWORD *)(a2 + 56),
          *(_DWORD *)(v9 + 40),
          *(_DWORD *)(v9 + 20),
          *(_DWORD *)(v9 + 16));
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, a2, v5);
  return v5;
}

```

## disassembly

```asm
0x1400399f0  push    rbx
0x1400399f2  push    rbp
0x1400399f3  push    rsi
0x1400399f4  push    rdi
0x1400399f5  push    r12
0x1400399f7  push    r14
0x1400399f9  push    r15
0x1400399fb  sub     rsp, 50h
0x1400399ff  mov     rdi, [rdx+38h]
0x140039a03  lea     r15, [rcx+378h]
0x140039a0a  mov     rsi, rdx
0x140039a0d  mov     rbx, rcx
0x140039a10  mov     ebp, 0C000009Ah
0x140039a15  add     rdi, 168h
0x140039a1c  jz      short loc_140039A27
0x140039a1e  mov     [rcx+360h], rdi
0x140039a25  jmp     short loc_140039A2E
0x140039a27  mov     rdi, [rcx+360h]
0x140039a2e  mov     rcx, r15
0x140039a31  call    MRxSmbSetInitialSMB
0x140039a36  movzx   edi, word ptr [rdi]
0x140039a39  add     edi, 0Eh
0x140039a3c  lea     r14d, [rdi+3]
0x140039a40  and     r14d, 0FFFFFFFCh
0x140039a44  add     r14d, 40h ; '@'
0x140039a48  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039a4f  lea     r12, WPP_GLOBAL_Control
0x140039a56  cmp     rcx, r12
0x140039a59  jz      short loc_140039A85
0x140039a5b  test    dword ptr [rcx+2Ch], 400h
0x140039a62  jz      short loc_140039A85
0x140039a64  mov     rcx, [rcx+18h]
0x140039a68  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140039a6f  mov     edx, 60h ; '`'
0x140039a74  mov     [rsp+88h+var_60], edi
0x140039a78  mov     r9, rsi
0x140039a7b  mov     dword ptr [rsp+88h+var_68], r14d
0x140039a80  call    WPP_SF_qDD
0x140039a85  cmp     r14d, [rbx+170h]
0x140039a8c  ja      loc_140039B52
0x140039a92  mov     r9d, 1
0x140039a98  lea     rax, MRxSmbFixupFindFirst
0x140039a9f  mov     [rsp+88h+var_48], rax; __int64
0x140039aa4  mov     rdx, rsi
0x140039aa7  mov     rax, [r15+18h]
0x140039aab  mov     rcx, rbx; pContext
0x140039aae  mov     [rsp+88h+var_60], edi; int
0x140039ab2  lea     r8d, [r9+0Fh]
0x140039ab6  mov     [rsp+88h+var_68], rax; __int64
0x140039abb  call    __MRxSmbSimpleSyncTransact2
0x140039ac0  mov     ebp, eax
0x140039ac2  test    eax, eax
0x140039ac4  jnz     loc_140039B52
0x140039aca  mov     r8, [r15+20h]
0x140039ace  mov     r9, [rsi+1C8h]
0x140039ad5  movzx   edx, word ptr [r8+2Fh]
0x140039ada  mov     rcx, [rdx+r8+8]
0x140039adf  mov     [r9], rcx
0x140039ae2  mov     rcx, [rdx+r8+10h]
0x140039ae7  mov     [r9+8], rcx
0x140039aeb  mov     rcx, [rdx+r8+18h]
0x140039af0  mov     [r9+10h], rcx
0x140039af4  mov     rax, [rdx+r8+20h]
0x140039af9  mov     [r9+18h], rax
0x140039afd  mov     eax, [rdx+r8+38h]
0x140039b02  mov     [r9+30h], eax
0x140039b06  mov     rax, [rdx+r8+28h]
0x140039b0b  mov     [r9+28h], rax
0x140039b0f  mov     rax, [rdx+r8+30h]
0x140039b14  mov     [r9+20h], rax
0x140039b18  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039b1f  cmp     rcx, r12
0x140039b22  jz      short loc_140039B83
0x140039b24  test    dword ptr [rcx+2Ch], 200h
0x140039b2b  jz      short loc_140039B52
0x140039b2d  mov     eax, [r9+10h]
0x140039b31  mov     rcx, [rcx+18h]
0x140039b35  mov     [rsp+88h+var_58], eax
0x140039b39  mov     eax, [r9+14h]
0x140039b3d  mov     [rsp+88h+var_60], eax
0x140039b41  mov     eax, [r9+28h]
0x140039b45  mov     r9, [rsi+38h]
0x140039b49  mov     dword ptr [rsp+88h+var_68], eax
0x140039b4d  call    WPP_SF_qDDD
0x140039b52  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039b59  cmp     rcx, r12
0x140039b5c  jz      short loc_140039B83
0x140039b5e  test    dword ptr [rcx+2Ch], 400h
0x140039b65  jz      short loc_140039B83
0x140039b67  mov     rcx, [rcx+18h]
0x140039b6b  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140039b72  mov     edx, 62h ; 'b'
0x140039b77  mov     dword ptr [rsp+88h+var_68], ebp
0x140039b7b  mov     r9, rsi
0x140039b7e  call    WPP_SF_qD
0x140039b83  mov     eax, ebp
0x140039b85  add     rsp, 50h
0x140039b89  pop     r15
0x140039b8b  pop     r14
0x140039b8d  pop     r12
0x140039b8f  pop     rdi
0x140039b90  pop     rsi
0x140039b91  pop     rbp
0x140039b92  pop     rbx
0x140039b93  retn
```
