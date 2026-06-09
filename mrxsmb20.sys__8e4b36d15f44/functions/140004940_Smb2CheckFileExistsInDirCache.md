# Smb2CheckFileExistsInDirCache

- ea: `0x140004940`
- end: `0x140004b25`
- name: `Smb2CheckFileExistsInDirCache`
- size: `485`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400236b0`

## callees

- `0x140004940`
- `0x140004b30`
- `0x140004d30`
- `0x140004f20`
- `0x140035464`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x140004a99`
- `ntoskrnl!ExReleasePushLockEx` at `0x140004a99`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004a57`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004a57`
- `rdbss!RxCrackPathName` at `0x1400049bd`
- `rdbss!RxCrackPathName` at `0x1400049bd`

## pseudocode

```c
__int64 __fastcall Smb2CheckFileExistsInDirCache(_QWORD *a1, __int64 a2, char a3)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v6; // rsi
  __int64 v7; // r12
  unsigned int *v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rbp
  char v11; // r15
  int v12; // edx
  int v13; // r8d
  int v14; // eax
  unsigned int v15; // esi
  __int64 DirCacheObject; // rax
  UNICODE_STRING String1; // [rsp+40h] [rbp-78h] BYREF
  __int128 v19; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v20[5]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v21; // [rsp+D0h] [rbp+18h] BYREF

  LOBYTE(v21) = a3;
  v3 = a1[7];
  v4 = a1[9];
  LODWORD(v21) = 0;
  v6 = *(_QWORD *)(v3 + 136);
  v7 = v3 + 360;
  v8 = 0;
  v9 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 40LL);
  v10 = *(_QWORD *)(v9 + 424);
  v19 = 0;
  String1 = 0;
  v20[0] = 0;
  v11 = (*(_BYTE *)(v3 + 355) & 0x3C) != 12;
  RxCrackPathName(v3 + 360, &v19, &String1, v20);
  if ( !String1.Length )
  {
LABEL_9:
    v15 = -1073741802;
    goto LABEL_4;
  }
  v14 = *(_DWORD *)(v6 + 8);
  v15 = -1073741802;
  if ( (v14 & 1) != 0 )
    goto LABEL_4;
  DirCacheObject = Smb2FindOrCreateDirCacheObject(
                     a1,
                     (struct _NAME_CACHE_CONTROL_ *)(v10 + 1112),
                     (__int64)&v19,
                     0,
                     0,
                     0);
  v8 = (unsigned int *)DirCacheObject;
  if ( !DirCacheObject || *(_DWORD *)(DirCacheObject + 32) )
    goto LABEL_4;
  ExAcquirePushLockSharedEx(DirCacheObject + 104, 0);
  v15 = QueryFileInfoFromDirectoryCache(v8, &String1, v11, 4u, 0, 0, &v21);
  ExReleasePushLockEx(v8 + 26, 0);
  if ( v15 == -1073741275 || v15 == -1073741533 )
  {
    if ( !v8[17] )
    {
      _InterlockedIncrement64((volatile signed __int64 *)(v9 + 560));
      v15 = -1073741772;
      goto LABEL_4;
    }
    goto LABEL_9;
  }
  if ( v15 == -1073741789 )
    v15 = LOWORD(v20[0]) != 0 ? 0xC0000016 : 0;
LABEL_4:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DqZ(WPP_GLOBAL_Control->AttachedDevice, v12, v13, v15, (char)v8, v7);
  }
  if ( v8 )
    Smb2DereferenceDirCacheObject(v8);
  return v15;
}

```

## disassembly

```asm
0x140004940  mov     r11, rsp
0x140004943  mov     [r11+18h], r8b
0x140004947  push    rbx
0x140004948  push    rbp
0x140004949  push    rsi
0x14000494a  push    rdi
0x14000494b  push    r12
0x14000494d  push    r13
0x14000494f  push    r14
0x140004951  push    r15
0x140004953  sub     rsp, 78h
0x140004957  mov     r8, [rcx+38h]
0x14000495b  lea     r9, [r11-58h]
0x14000495f  mov     rax, [rcx+48h]
0x140004963  xorps   xmm0, xmm0
0x140004966  xor     r13d, r13d
0x140004969  xorps   xmm1, xmm1
0x14000496c  mov     rdi, rcx
0x14000496f  mov     [r11+18h], r13d
0x140004973  mov     rsi, [r8+88h]
0x14000497a  lea     r12, [r8+168h]
0x140004981  mov     rdx, [rax+28h]
0x140004985  mov     rcx, r12
0x140004988  mov     ebx, r13d
0x14000498b  mov     r14, [rdx+28h]
0x14000498f  lea     rdx, [r11-68h]
0x140004993  mov     rbp, [r14+1A8h]
0x14000499a  movups  [rsp+0B8h+var_68], xmm0
0x14000499f  movups  xmmword ptr [rsp+0B8h+String1.Length], xmm1
0x1400049a4  movups  [rsp+0B8h+var_58], xmm0
0x1400049a9  movzx   eax, byte ptr [r8+163h]
0x1400049b1  lea     r8, [r11-78h]
0x1400049b5  and     al, 3Ch
0x1400049b7  cmp     al, 0Ch
0x1400049b9  setnz   r15b
0x1400049bd  call    cs:__imp_RxCrackPathName
0x1400049c4  nop     dword ptr [rax+rax+00h]
0x1400049c9  cmp     [rsp+0B8h+String1.Length], bx
0x1400049ce  jz      short loc_140004A4A
0x1400049d0  mov     eax, [rsi+8]
0x1400049d3  mov     esi, 0C0000016h
0x1400049d8  test    al, 1
0x1400049da  jnz     short loc_140004A09
0x1400049dc  lea     rdx, [rbp+458h]
0x1400049e3  mov     [rsp+0B8h+var_90], r13
0x1400049e8  xor     r9d, r9d
0x1400049eb  mov     [rsp+0B8h+var_98], r13
0x1400049f0  lea     r8, [rsp+0B8h+var_68]
0x1400049f5  mov     rcx, rdi
0x1400049f8  call    Smb2FindOrCreateDirCacheObject
0x1400049fd  mov     rbx, rax
0x140004a00  test    rax, rax
0x140004a03  jnz     loc_140004AE7
0x140004a09  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004a10  lea     rax, WPP_GLOBAL_Control
0x140004a17  cmp     rcx, rax
0x140004a1a  jz      short loc_140004A29
0x140004a1c  test    dword ptr [rcx+2Ch], 100h
0x140004a23  jnz     loc_140004B00
0x140004a29  test    rbx, rbx
0x140004a2c  jz      short loc_140004A36
0x140004a2e  mov     rcx, rbx; P
0x140004a31  call    Smb2DereferenceDirCacheObject
0x140004a36  mov     eax, esi
0x140004a38  add     rsp, 78h
0x140004a3c  pop     r15
0x140004a3e  pop     r14
0x140004a40  pop     r13
0x140004a42  pop     r12
0x140004a44  pop     rdi
0x140004a45  pop     rsi
0x140004a46  pop     rbp
0x140004a47  pop     rbx
0x140004a48  retn
0x140004a4a  mov     esi, 0C0000016h
0x140004a4f  jmp     short loc_140004A09
0x140004a51  xor     edx, edx
0x140004a53  lea     rcx, [rax+68h]
0x140004a57  call    cs:__imp_ExAcquirePushLockSharedEx
0x140004a5e  nop     dword ptr [rax+rax+00h]
0x140004a63  lea     rax, [rsp+0B8h+arg_10]
0x140004a6b  mov     r9d, 4
0x140004a71  mov     [rsp+0B8h+var_88], rax; __int64
0x140004a76  lea     rdx, [rsp+0B8h+String1]; String1
0x140004a7b  mov     [rsp+0B8h+var_90], r13; __int64
0x140004a80  movzx   r8d, r15b
0x140004a84  mov     rcx, rbx; Context
0x140004a87  mov     [rsp+0B8h+var_98], r13; __int64
0x140004a8c  call    QueryFileInfoFromDirectoryCache
0x140004a91  xor     edx, edx
0x140004a93  lea     rcx, [rbx+68h]
0x140004a97  mov     esi, eax
0x140004a99  call    cs:__imp_ExReleasePushLockEx
0x140004aa0  nop     dword ptr [rax+rax+00h]
0x140004aa5  cmp     esi, 0C0000225h
0x140004aab  jnz     short loc_140004AF6
0x140004aad  mov     eax, [rbx+44h]
0x140004ab0  test    eax, eax
0x140004ab2  jnz     short loc_140004A4A
0x140004ab4  lock inc qword ptr [r14+230h]
0x140004abc  mov     esi, 0C0000034h
0x140004ac1  jmp     loc_140004A09
0x140004ac6  cmp     esi, 0C0000023h
0x140004acc  jnz     loc_140004A09
0x140004ad2  movzx   eax, word ptr [rsp+0B8h+var_58]
0x140004ad7  neg     ax
0x140004ada  sbb     esi, esi
0x140004adc  and     esi, 0C0000016h
0x140004ae2  jmp     loc_140004A09
0x140004ae7  cmp     [rax+20h], r13d
0x140004aeb  jnz     loc_140004A09
0x140004af1  jmp     loc_140004A51
0x140004af6  cmp     esi, 0C0000123h
0x140004afc  jz      short loc_140004AAD
0x140004afe  jmp     short loc_140004AC6
0x140004b00  cmp     byte ptr [rcx+29h], 2
0x140004b04  jb      loc_140004A29
0x140004b0a  mov     rcx, [rcx+18h]
0x140004b0e  mov     r9d, esi
0x140004b11  mov     [rsp+0B8h+var_90], r12
0x140004b16  mov     [rsp+0B8h+var_98], rbx
0x140004b1b  call    WPP_SF_DqZ
0x140004b20  jmp     loc_140004A29
```
