# CscDclMRxWriteStoreData

- ea: `0x140019bbc`
- end: `0x140019f1d`
- name: `CscDclMRxWriteStoreData`
- size: `865`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14007ae70`

## callees

- `0x140003a00`
- `0x1400053f8`
- `0x14000e070`
- `0x140012cb0`
- `0x1400169d4`
- `0x140018930`
- `0x140019bbc`
- `0x14001a494`
- `0x14001aba0`
- `0x14001b4f4`
- `0x14002f010`

## import_xrefs

- `rdbss!RxReleaseFcbPagingInMRx` at `0x140019d8c`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x140019d8c`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x140019d3c`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x140019d3c`

## pseudocode

```c
__int64 __fastcall CscDclMRxWriteStoreData(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // r14
  __int64 v5; // rdi
  int v8; // ebx
  int v10; // r9d
  __int64 v11; // r9
  unsigned int v12; // ebx
  __int64 v13; // r15
  __int64 v14; // r8
  __int64 v15; // rdi
  int v16; // eax
  int v17; // r8d
  int v18; // edx
  char v19; // dl
  char v20; // cl
  int v21; // eax
  int v22; // ecx
  char v23; // r10
  int v25; // [rsp+20h] [rbp-69h]
  int v26; // [rsp+28h] [rbp-61h]
  int v27; // [rsp+30h] [rbp-59h]
  int v28; // [rsp+50h] [rbp-39h] BYREF
  __int128 v29; // [rsp+58h] [rbp-31h] BYREF
  __int128 v30; // [rsp+68h] [rbp-21h]
  __int128 v31; // [rsp+80h] [rbp-9h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v5 = *(_QWORD *)(a1 + 72);
  v29 = 0;
  v8 = a2;
  v30 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qiqD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, a3, a4);
  LOBYTE(a2) = 1;
  CscDclMRx_Synchronize(a1, a2, 0);
  CscGetContextsEx(a1, *(_QWORD *)(a1 + 56), &v29);
  LOBYTE(v10) = 1;
  CscUpdateAndCaptureConnectionStateEx(v4, v5, a1, v10, (__int64)&v31, 1);
  if ( (BYTE1(v31) & 0x40) != 0 )
  {
    v12 = (BYTE2(v31) & 1) != 0 ? -1073741628 : -1073741300;
  }
  else
  {
    v13 = v30;
    v14 = 0;
    v15 = *((_QWORD *)&v29 + 1);
    if ( (_QWORD)v30
      && *(_QWORD *)(v30 + 8)
      && (v31 & 8) != 0
      && ((v16 = *(_DWORD *)(v4 + 164), (v16 & 2) != 0) || (v16 & 1) != 0)
      && (_m_prefetchw((const void *)(*((_QWORD *)&v29 + 1) + 96LL)),
          (_InterlockedXor((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 96LL), 0) & 2) == 0)
      && (*(_BYTE *)(v4 + 256) & 1) == 0 )
    {
      v28 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids);
      _InterlockedOr((volatile signed __int32 *)(v15 + 96), 8u);
      LOBYTE(v14) = 1;
      RxAcquireExclusiveFcbPagingInMRx(a1, v4, v14);
      LOBYTE(v17) = 1;
      LOBYTE(v18) = (v31 & 0x10) != 0;
      v12 = CscEnWriteData(*(_QWORD *)(v13 + 8), v18, v17, v8, a4, a3, 0, (__int64)&v28, 0, 0);
      RxReleaseFcbPagingInMRx(a1, v4);
      if ( ((v12 & 0x80000000) != 0 || v28 != a4)
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_DDd(
          WPP_GLOBAL_Control->AttachedDevice,
          60,
          WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
          v12,
          v28,
          a4);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        v19 = *(_BYTE *)(v4 + 256) & 1;
        _m_prefetchw((const void *)(v15 + 96));
        v20 = _InterlockedXor((volatile signed __int32 *)(v15 + 96), 0);
        LOBYTE(v11) = 89;
        v21 = *(_DWORD *)(v4 + 164);
        v22 = v20 & 2;
        if ( (v21 & 2) != 0 || (v23 = 78, (v21 & 1) != 0) )
          v23 = 89;
        if ( !v13 || !*(_QWORD *)(v13 + 8) )
          LOBYTE(v11) = 78;
        LOBYTE(v27) = v22 != 0 ? 89 : 78;
        LOBYTE(v26) = v23;
        LOBYTE(v25) = (v31 & 8) != 0 ? 89 : 78;
        WPP_SF_ccccc(
          WPP_GLOBAL_Control->AttachedDevice,
          61,
          WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
          v11,
          v25,
          v26,
          v27,
          v19 != 0 ? 89 : 78);
      }
      v12 = -1073741300;
    }
  }
  CscDclMRx_Synchronize(a1, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x140019bbc  push    rbp
0x140019bbe  push    rbx
0x140019bbf  push    rsi
0x140019bc0  push    rdi
0x140019bc1  push    r12
0x140019bc3  push    r13
0x140019bc5  push    r14
0x140019bc7  push    r15
0x140019bc9  lea     rbp, [rsp-1Fh]
0x140019bce  sub     rsp, 0A8h
0x140019bd5  mov     rax, cs:__security_cookie
0x140019bdc  xor     rax, rsp
0x140019bdf  mov     [rbp+57h+var_50], rax
0x140019be3  mov     r14, [rcx+38h]
0x140019be7  xorps   xmm0, xmm0
0x140019bea  mov     rdi, [rcx+48h]
0x140019bee  mov     r12d, r9d
0x140019bf1  movups  [rbp+57h+var_88], xmm0
0x140019bf5  mov     r13, r8
0x140019bf8  mov     rbx, rdx
0x140019bfb  movups  [rbp+57h+var_78], xmm0
0x140019bff  mov     rsi, rcx
0x140019c02  movups  [rbp+57h+var_60], xmm0
0x140019c06  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c0d  lea     rax, WPP_GLOBAL_Control
0x140019c14  cmp     rcx, rax
0x140019c17  jz      short loc_140019C3B
0x140019c19  mov     eax, [rcx+2Ch]
0x140019c1c  test    al, 20h
0x140019c1e  jz      short loc_140019C3B
0x140019c20  mov     rcx, [rcx+18h]
0x140019c24  mov     dword ptr [rsp+0E0h+var_B0], r9d
0x140019c29  mov     r9, rsi
0x140019c2c  mov     [rsp+0E0h+var_B8], r8
0x140019c31  mov     [rsp+0E0h+var_C0], rdx
0x140019c36  call    WPP_SF_qiqD
0x140019c3b  xor     r8d, r8d
0x140019c3e  mov     dl, 1
0x140019c40  mov     rcx, rsi
0x140019c43  call    CscDclMRx_Synchronize
0x140019c48  mov     rdx, [rsi+38h]
0x140019c4c  lea     r8, [rbp+57h+var_88]
0x140019c50  mov     rcx, rsi
0x140019c53  call    CscGetContextsEx
0x140019c58  lea     rax, [rbp+57h+var_60]
0x140019c5c  mov     byte ptr [rsp+0E0h+var_B8], 1
0x140019c61  mov     r9b, 1
0x140019c64  mov     [rsp+0E0h+var_C0], rax
0x140019c69  mov     r8, rsi
0x140019c6c  mov     rdx, rdi
0x140019c6f  mov     rcx, r14
0x140019c72  call    CscUpdateAndCaptureConnectionStateEx
0x140019c77  test    byte ptr [rbp+57h+var_60+1], 40h
0x140019c7b  jz      short loc_140019C97
0x140019c7d  mov     al, byte ptr [rbp+57h+var_60+2]
0x140019c80  and     al, 1
0x140019c82  neg     al
0x140019c84  sbb     ebx, ebx
0x140019c86  and     ebx, 0FFFFFEB8h
0x140019c8c  add     ebx, 0C000020Ch
0x140019c92  jmp     loc_140019EBB
0x140019c97  mov     r15, qword ptr [rbp+57h+var_78]
0x140019c9b  xor     r8d, r8d
0x140019c9e  mov     rdi, qword ptr [rbp+57h+var_88+8]
0x140019ca2  test    r15, r15
0x140019ca5  jz      loc_140019DF2
0x140019cab  cmp     [r15+8], r8
0x140019caf  jz      loc_140019DF2
0x140019cb5  test    byte ptr [rbp+57h+var_60], 8
0x140019cb9  jz      loc_140019DF2
0x140019cbf  mov     eax, [r14+0A4h]
0x140019cc6  test    al, 2
0x140019cc8  jnz     short loc_140019CD2
0x140019cca  test    al, 1
0x140019ccc  jz      loc_140019DF2
0x140019cd2  prefetchw byte ptr [rdi+60h]
0x140019cd6  mov     eax, [rdi+60h]
0x140019cd9  mov     ecx, eax
0x140019cdb  xor     ecx, r8d
0x140019cde  lock cmpxchg [rdi+60h], ecx
0x140019ce3  jnz     short loc_140019CD9
0x140019ce5  test    al, 2
0x140019ce7  jnz     loc_140019DF2
0x140019ced  test    byte ptr [r14+100h], 1
0x140019cf5  jnz     loc_140019DF2
0x140019cfb  mov     [rbp+57h+var_90], r8d
0x140019cff  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d06  lea     rdx, WPP_GLOBAL_Control
0x140019d0d  cmp     rcx, rdx
0x140019d10  jz      short loc_140019D2E
0x140019d12  mov     eax, [rcx+2Ch]
0x140019d15  test    al, 40h
0x140019d17  jz      short loc_140019D2E
0x140019d19  mov     rcx, [rcx+18h]
0x140019d1d  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x140019d24  mov     edx, 3Bh ; ';'
0x140019d29  call    WPP_SF_
0x140019d2e  lock or dword ptr [rdi+60h], 8
0x140019d33  mov     r8b, 1
0x140019d36  mov     rdx, r14
0x140019d39  mov     rcx, rsi
0x140019d3c  call    cs:__imp_RxAcquireExclusiveFcbPagingInMRx
0x140019d43  nop     dword ptr [rax+rax+00h]
0x140019d48  mov     dl, byte ptr [rbp+57h+var_60]
0x140019d4b  lea     rax, [rbp+57h+var_90]
0x140019d4f  mov     rcx, [r15+8]
0x140019d53  xor     edi, edi
0x140019d55  mov     [rsp+0E0h+var_98], rdi
0x140019d5a  mov     r9, rbx
0x140019d5d  mov     [rsp+0E0h+var_A0], rdi
0x140019d62  mov     r8b, 1
0x140019d65  mov     [rsp+0E0h+var_A8], rax
0x140019d6a  shr     dl, 4
0x140019d6d  mov     [rsp+0E0h+var_B0], rdi
0x140019d72  and     dl, 1
0x140019d75  mov     [rsp+0E0h+var_B8], r13
0x140019d7a  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x140019d7f  call    CscEnWriteData
0x140019d84  mov     rdx, r14
0x140019d87  mov     rcx, rsi
0x140019d8a  mov     ebx, eax
0x140019d8c  call    cs:__imp_RxReleaseFcbPagingInMRx
0x140019d93  nop     dword ptr [rax+rax+00h]
0x140019d98  mov     r8d, [rbp+57h+var_90]
0x140019d9c  test    ebx, ebx
0x140019d9e  js      short loc_140019DA9
0x140019da0  cmp     r8d, r12d
0x140019da3  jz      loc_140019EBB
0x140019da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140019db0  lea     rax, WPP_GLOBAL_Control
0x140019db7  cmp     rcx, rax
0x140019dba  jz      loc_140019EBB
0x140019dc0  mov     eax, [rcx+2Ch]
0x140019dc3  test    al, 20h
0x140019dc5  jz      loc_140019EBB
0x140019dcb  mov     rcx, [rcx+18h]
0x140019dcf  mov     edx, 3Ch ; '<'
0x140019dd4  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x140019dd9  mov     r9d, ebx
0x140019ddc  mov     dword ptr [rsp+0E0h+var_C0], r8d
0x140019de1  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x140019de8  call    WPP_SF_DDd
0x140019ded  jmp     loc_140019EBB
0x140019df2  mov     rax, cs:WPP_GLOBAL_Control
0x140019df9  lea     rdx, WPP_GLOBAL_Control
0x140019e00  cmp     rax, rdx
0x140019e03  jz      loc_140019EB6
0x140019e09  mov     eax, [rax+2Ch]
0x140019e0c  test    al, 20h
0x140019e0e  jz      loc_140019EB6
0x140019e14  mov     dl, [r14+100h]
0x140019e1b  mov     r11b, 1
0x140019e1e  and     dl, r11b
0x140019e21  prefetchw byte ptr [rdi+60h]
0x140019e25  mov     eax, [rdi+60h]
0x140019e28  mov     ecx, eax
0x140019e2a  xor     ecx, r8d
0x140019e2d  lock cmpxchg [rdi+60h], ecx
0x140019e32  jnz     short loc_140019E28
0x140019e34  mov     ecx, eax
0x140019e36  mov     r9b, 59h ; 'Y'
0x140019e39  mov     eax, [r14+0A4h]
0x140019e40  and     ecx, 2
0x140019e43  mov     bl, 4Eh ; 'N'
0x140019e45  test    al, 2
0x140019e47  jnz     short loc_140019E51
0x140019e49  mov     r10b, bl
0x140019e4c  test    r11b, al
0x140019e4f  jz      short loc_140019E54
0x140019e51  mov     r10b, r9b
0x140019e54  mov     al, byte ptr [rbp+57h+var_60]
0x140019e57  shr     al, 3
0x140019e5a  and     al, r11b
0x140019e5d  test    r15, r15
0x140019e60  jz      short loc_140019E68
0x140019e62  cmp     [r15+8], r8
0x140019e66  jnz     short loc_140019E6B
0x140019e68  mov     r9b, bl
0x140019e6b  neg     dl
0x140019e6d  mov     dl, 0Bh
0x140019e6f  sbb     r8b, r8b
0x140019e72  and     r8b, dl
0x140019e75  add     r8b, bl
0x140019e78  neg     ecx
0x140019e7a  mov     byte ptr [rsp+0E0h+var_A8], r8b
0x140019e7f  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x140019e86  sbb     cl, cl
0x140019e88  and     cl, dl
0x140019e8a  add     cl, bl
0x140019e8c  mov     byte ptr [rsp+0E0h+var_B0], cl
0x140019e90  neg     al
0x140019e92  mov     rcx, cs:WPP_GLOBAL_Control
0x140019e99  sbb     al, al
0x140019e9b  mov     byte ptr [rsp+0E0h+var_B8], r10b
0x140019ea0  and     al, dl
0x140019ea2  mov     edx, 3Dh ; '='
0x140019ea7  add     al, bl
0x140019ea9  mov     rcx, [rcx+18h]
0x140019ead  mov     byte ptr [rsp+0E0h+var_C0], al
0x140019eb1  call    WPP_SF_ccccc
0x140019eb6  mov     ebx, 0C000020Ch
0x140019ebb  xor     r8d, r8d
0x140019ebe  xor     edx, edx
0x140019ec0  mov     rcx, rsi
0x140019ec3  call    CscDclMRx_Synchronize
0x140019ec8  mov     rcx, cs:WPP_GLOBAL_Control
0x140019ecf  lea     rax, WPP_GLOBAL_Control
0x140019ed6  cmp     rcx, rax
0x140019ed9  jz      short loc_140019EFA
0x140019edb  mov     eax, [rcx+2Ch]
0x140019ede  test    al, 20h
0x140019ee0  jz      short loc_140019EFA
0x140019ee2  mov     rcx, [rcx+18h]
0x140019ee6  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x140019eed  mov     edx, 3Eh ; '>'
0x140019ef2  mov     r9d, ebx
0x140019ef5  call    WPP_SF_d
0x140019efa  mov     eax, ebx
0x140019efc  mov     rcx, [rbp+57h+var_50]
0x140019f00  xor     rcx, rsp; StackCookie
0x140019f03  call    __security_check_cookie
0x140019f08  add     rsp, 0A8h
0x140019f0f  pop     r15
0x140019f11  pop     r14
0x140019f13  pop     r13
0x140019f15  pop     r12
0x140019f17  pop     rdi
0x140019f18  pop     rsi
0x140019f19  pop     rbx
0x140019f1a  pop     rbp
0x140019f1b  retn
```
