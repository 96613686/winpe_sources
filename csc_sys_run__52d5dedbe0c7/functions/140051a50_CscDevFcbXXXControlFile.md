# CscDevFcbXXXControlFile

- ea: `0x140051a50`
- end: `0x140051c93`
- name: `CscDevFcbXXXControlFile`
- size: `579`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140003a00`
- `0x14000e100`
- `0x1400190ec`
- `0x140020028`
- `0x14002f010`
- `0x140051a50`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140051bf4`
- `ntoskrnl!ProbeForWrite` at `0x140051bf4`
- `rdbss!RxFinalizeConnection` at `0x140051bb6`
- `rdbss!RxFinalizeConnection` at `0x140051bb6`

## pseudocode

```c
__int64 __fastcall CscDevFcbXXXControlFile(__int64 a1)
{
  __int64 v2; // r14
  __int64 v3; // r9
  _BOOL8 v4; // r8
  unsigned int v5; // r15d
  LOGICAL v6; // esi
  unsigned int v7; // ebx
  int v8; // ecx
  unsigned int v9; // ecx
  __int64 v10; // rbx
  _BYTE v12[16]; // [rsp+48h] [rbp-80h] BYREF
  __int128 v13; // [rsp+58h] [rbp-70h]
  __int128 v14; // [rsp+70h] [rbp-58h] BYREF

  v2 = *(_QWORD *)(a1 + 72);
  v3 = *(unsigned int *)(*(_QWORD *)(a1 + 48) + 24LL);
  v4 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v14 = 0;
  v13 = 0;
  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qDqd(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      (unsigned int)WPP_3708ac913792321e66f761dcbaa4d787_Traceguids,
      *(_QWORD *)(a1 + 40),
      v3,
      v2,
      v4);
  CscGetContexts(a1, v12, v4, v3);
  if ( !v2 || (v6 = 1, (_QWORD)v13) && (*(_DWORD *)(v13 + 24) & 1) != 0 )
  {
    v7 = -1073741811;
  }
  else
  {
    CscUpdateAndCaptureConnectionStateEx(*(_QWORD *)(a1 + 56), v2, a1, 0, (__int64)&v14, 1);
    v7 = -1073741808;
    if ( (v14 & 0x10) != 0 )
    {
      if ( *(_BYTE *)(a1 + 32) == 13 && !*(_BYTE *)(a1 + 576) )
      {
        if ( *(_DWORD *)(a1 + 540) == 1311139 )
        {
          v9 = *(_DWORD *)(a1 + 568);
          *(_QWORD *)(a1 + 184) = 0;
          if ( v9 < 0x24 )
          {
            v7 = -1073741789;
          }
          else
          {
            v10 = *(_QWORD *)(a1 + 552);
            if ( *(_BYTE *)(*(_QWORD *)(a1 + 40) + 64LL) )
              ProbeForWrite(*(volatile void **)(a1 + 552), v9, 4u);
            if ( *(_DWORD *)(v10 + 4) == 6 )
            {
              *(_QWORD *)(v10 + 24) = 0;
              v7 = 0;
            }
            else
            {
              v7 = -1073741811;
            }
          }
        }
        else if ( *(_DWORD *)(a1 + 540) == 1311148 && *(_DWORD *)(a1 + 568) >= 0x24u )
        {
          v8 = *(_DWORD *)(*(_QWORD *)(a1 + 552) + 8LL);
          if ( v8 != 2 )
            v6 = (unsigned __int8)-(v8 != 0);
          v7 = RxFinalizeConnection(*(PNET_ROOT *)(*(_QWORD *)(v2 + 40) + 32LL), *(PV_NET_ROOT *)(v2 + 40), v6);
        }
      }
    }
    else
    {
      v5 = 473;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_3708ac913792321e66f761dcbaa4d787_Traceguids, v5, v7);
  return v7;
}

```

## disassembly

```asm
0x140051a50  push    rbx
0x140051a52  push    rsi
0x140051a53  push    rdi
0x140051a54  push    r12
0x140051a56  push    r14
0x140051a58  push    r15
0x140051a5a  sub     rsp, 98h
0x140051a61  mov     rax, cs:__security_cookie
0x140051a68  xor     rax, rsp
0x140051a6b  mov     [rsp+0C8h+var_48], rax
0x140051a73  mov     rdi, rcx
0x140051a76  mov     r14, [rcx+48h]
0x140051a7a  mov     rax, [rcx+30h]
0x140051a7e  mov     r9d, [rax+18h]
0x140051a82  xor     r8d, r8d
0x140051a85  mov     rax, cs:CscDeviceObject
0x140051a8c  cmp     [rcx+50h], rax
0x140051a90  setnz   r8b
0x140051a94  xorps   xmm0, xmm0
0x140051a97  movups  [rsp+0C8h+var_58], xmm0
0x140051a9c  xorps   xmm1, xmm1
0x140051a9f  movups  [rsp+0C8h+var_70], xmm1
0x140051aa4  xor     r15d, r15d
0x140051aa7  mov     [rsp+0C8h+var_84], r15d
0x140051aac  lea     r12, WPP_GLOBAL_Control
0x140051ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x140051aba  cmp     rcx, r12
0x140051abd  jz      short loc_140051AED
0x140051abf  mov     eax, [rcx+2Ch]
0x140051ac2  test    al, 20h
0x140051ac4  jz      short loc_140051AED
0x140051ac6  lea     edx, [r15+11h]
0x140051aca  mov     [rsp+0C8h+var_98], r8d
0x140051acf  mov     [rsp+0C8h+var_A0], r14
0x140051ad4  mov     dword ptr [rsp+0C8h+var_A8], r9d
0x140051ad9  mov     r9, [rdi+28h]
0x140051add  lea     r8, WPP_3708ac913792321e66f761dcbaa4d787_Traceguids
0x140051ae4  mov     rcx, [rcx+18h]
0x140051ae8  call    WPP_SF_qDqd
0x140051aed  lea     rdx, [rsp+0C8h+var_80]
0x140051af2  mov     rcx, rdi
0x140051af5  call    CscGetContexts
0x140051afa  test    r14, r14
0x140051afd  jz      loc_140051C3B
0x140051b03  mov     rax, qword ptr [rsp+0C8h+var_70]
0x140051b08  mov     esi, 1
0x140051b0d  test    rax, rax
0x140051b10  jz      short loc_140051B1E
0x140051b12  mov     eax, [rax+18h]
0x140051b15  test    sil, al
0x140051b18  jnz     loc_140051C3B
0x140051b1e  mov     byte ptr [rsp+0C8h+var_A0], sil
0x140051b23  lea     rax, [rsp+0C8h+var_58]
0x140051b28  mov     [rsp+0C8h+var_A8], rax
0x140051b2d  xor     r9d, r9d
0x140051b30  mov     r8, rdi
0x140051b33  mov     rdx, r14
0x140051b36  mov     rcx, [rdi+38h]
0x140051b3a  call    CscUpdateAndCaptureConnectionStateEx
0x140051b3f  mov     ebx, 0C0000010h
0x140051b44  test    byte ptr [rsp+0C8h+var_58], 10h
0x140051b49  jnz     short loc_140051B56
0x140051b4b  mov     r15d, 1D9h
0x140051b51  jmp     loc_140051C40
0x140051b56  cmp     byte ptr [rdi+20h], 0Dh
0x140051b5a  jnz     loc_140051C40
0x140051b60  cmp     [rdi+240h], r15b
0x140051b67  jnz     loc_140051C40
0x140051b6d  mov     ecx, [rdi+21Ch]
0x140051b73  sub     ecx, 1401A3h
0x140051b79  jz      short loc_140051BC6
0x140051b7b  cmp     ecx, 9
0x140051b7e  jnz     loc_140051C40
0x140051b84  cmp     dword ptr [rdi+238h], 24h ; '$'
0x140051b8b  jb      loc_140051C40
0x140051b91  mov     r9, [r14+28h]
0x140051b95  mov     rax, [rdi+228h]
0x140051b9c  mov     ecx, [rax+8]
0x140051b9f  cmp     ecx, 2
0x140051ba2  jz      short loc_140051BAC
0x140051ba4  neg     ecx
0x140051ba6  sbb     esi, esi
0x140051ba8  movzx   esi, sil
0x140051bac  mov     r8d, esi; ForceFilesClosed
0x140051baf  mov     rdx, r9; VNetRoot
0x140051bb2  mov     rcx, [r9+20h]; NetRoot
0x140051bb6  call    cs:__imp_RxFinalizeConnection
0x140051bbd  nop     dword ptr [rax+rax+00h]
0x140051bc2  mov     ebx, eax
0x140051bc4  jmp     short loc_140051C40
0x140051bc6  mov     ecx, [rdi+238h]
0x140051bcc  mov     [rdi+0B8h], r15
0x140051bd3  cmp     ecx, 24h ; '$'
0x140051bd6  jb      short loc_140051C34
0x140051bd8  mov     rbx, [rdi+228h]
0x140051bdf  mov     rax, [rdi+28h]
0x140051be3  cmp     byte ptr [rax+40h], 0
0x140051be7  jz      short loc_140051C00
0x140051be9  mov     edx, ecx; Length
0x140051beb  mov     r8d, 4; Alignment
0x140051bf1  mov     rcx, rbx; Address
0x140051bf4  call    cs:__imp_ProbeForWrite
0x140051bfb  nop     dword ptr [rax+rax+00h]
0x140051c00  cmp     dword ptr [rbx+4], 6
0x140051c04  jnz     short loc_140051C12
0x140051c06  mov     qword ptr [rbx+18h], 0
0x140051c0e  xor     ebx, ebx
0x140051c10  jmp     short loc_140051C17
0x140051c12  mov     ebx, 0C000000Dh
0x140051c17  mov     [rsp+0C8h+var_88], ebx
0x140051c1b  jmp     short loc_140051C40
0x140051c1d  mov     ebx, 0C000000Dh
0x140051c22  mov     [rsp+0C8h+var_88], ebx
0x140051c26  lea     r12, WPP_GLOBAL_Control
0x140051c2d  mov     r15d, [rsp+0C8h+var_84]
0x140051c32  jmp     short loc_140051C40
0x140051c34  mov     ebx, 0C0000023h
0x140051c39  jmp     short loc_140051C40
0x140051c3b  mov     ebx, 0C000000Dh
0x140051c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c47  cmp     rcx, r12
0x140051c4a  jz      short loc_140051C6F
0x140051c4c  mov     eax, [rcx+2Ch]
0x140051c4f  test    al, 20h
0x140051c51  jz      short loc_140051C6F
0x140051c53  mov     edx, 12h
0x140051c58  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x140051c5c  mov     r9d, r15d
0x140051c5f  lea     r8, WPP_3708ac913792321e66f761dcbaa4d787_Traceguids
0x140051c66  mov     rcx, [rcx+18h]
0x140051c6a  call    WPP_SF_Dd
0x140051c6f  mov     eax, ebx
0x140051c71  mov     rcx, [rsp+0C8h+var_48]
0x140051c79  xor     rcx, rsp; StackCookie
0x140051c7c  call    __security_check_cookie
0x140051c81  add     rsp, 98h
0x140051c88  pop     r15
0x140051c8a  pop     r14
0x140051c8c  pop     r12
0x140051c8e  pop     rdi
0x140051c8f  pop     rsi
0x140051c90  pop     rbx
0x140051c91  retn
```
