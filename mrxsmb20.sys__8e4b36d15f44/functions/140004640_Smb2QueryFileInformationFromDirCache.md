# Smb2QueryFileInformationFromDirCache

- ea: `0x140004640`
- end: `0x140004938`
- name: `Smb2QueryFileInformationFromDirCache`
- size: `760`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, _BYTE *, _DWORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x140003840`
- `0x140003a80`
- `0x140005820`
- `0x1400346c0`

## callees

- `0x140004640`
- `0x140004b30`
- `0x140004d30`
- `0x140004f20`
- `0x14000ad90`
- `0x14003581c`
- `0x140037120`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x1400047cf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400047cf`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004785`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140004785`
- `rdbss!RxCrackPathName` at `0x140004709`
- `rdbss!RxCrackPathName` at `0x140004709`

## pseudocode

```c
__int64 __fastcall Smb2QueryFileInformationFromDirCache(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _BYTE *a5,
        _DWORD *a6)
{
  _BYTE *v7; // r14
  __int64 v8; // rcx
  __int64 v10; // rdi
  unsigned int v11; // esi
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  char *v15; // rbx
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rdi
  int v19; // ecx
  _DWORD *v21; // rax
  int v22; // [rsp+28h] [rbp-E0h]
  _DWORD v23[3]; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B8h]
  _DWORD *v25; // [rsp+58h] [rbp-B0h]
  UNICODE_STRING String1; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+70h] [rbp-98h] BYREF
  __int128 v28; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v30; // [rsp+B0h] [rbp-58h]

  v7 = a5;
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL);
  v25 = a5;
  v24 = 0;
  v30 = 0;
  v10 = *(_QWORD *)(v8 + 40);
  v11 = -1073741802;
  v23[0] = *a6;
  v12 = *(_QWORD *)(a1 + 56);
  v13 = *(_QWORD *)(v10 + 424);
  v28 = 0;
  String1 = 0;
  *(_QWORD *)&v23[1] = v12 + 360;
  v27 = 0;
  memset(v29, 0, sizeof(v29));
  RxCrackPathName(v12 + 360, &v28, &String1, &v27);
  if ( String1.Length && !(_WORD)v27 )
  {
    if ( a4 == 35 )
    {
      v7 = v29;
      v23[0] = 40;
    }
    v14 = Smb2FindOrCreateDirCacheObject(a1, v13 + 1112, &v28, 0, 0, 0);
    v15 = (char *)v14;
    if ( !v14 || *(_DWORD *)(v14 + 32) )
    {
      v19 = v24;
    }
    else
    {
      _InterlockedIncrement64((volatile signed __int64 *)(v10 + 544));
      ExAcquirePushLockSharedEx(v14 + 104, 0);
      v11 = QueryFileInfoFromDirectoryCache(v15, &String1, 0, (__int64)v7, (__int64)v23);
      ExReleasePushLockEx(v15 + 104, 0);
      if ( v11 == -1073741275 || v11 == -1073741533 || v11 == -1073741821 )
      {
        v11 = -1073741802;
LABEL_20:
        Smb2DereferenceDirCacheObject(v15);
        return v11;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        v18 = *(_QWORD *)&v23[1];
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_qdZD(WPP_GLOBAL_Control->AttachedDevice, v16, v17, (_DWORD)v15, a4, *(__int64 *)&v23[1], v11);
      }
      else
      {
        v18 = *(_QWORD *)&v23[1];
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x200) != 0 )
      {
        LOWORD(v22) = *(_WORD *)v18 >> 1;
        McTemplateK0pphzr2q_EtwWriteTransfer(
          (unsigned __int16)v22,
          (unsigned int)SmbFetchDirCache,
          a1 + 412,
          a1,
          *(_QWORD *)(a1 + 56),
          v22,
          *(_QWORD *)(v18 + 8));
      }
      v19 = v30;
    }
    if ( a4 == 35 )
    {
      if ( v11 || (v19 & 0x400) != 0 )
      {
        v11 = -1073741802;
      }
      else if ( *a6 < 8u )
      {
        v11 = -1073741789;
      }
      else
      {
        v21 = v25;
        *v25 = v19;
        v21[1] = 0;
        *a6 -= 8;
      }
    }
    else
    {
      *a6 = v23[0];
    }
    if ( v15 )
      goto LABEL_20;
  }
  return v11;
}

```

## disassembly

```asm
0x140004640  mov     r11, rsp
0x140004643  push    rbx
0x140004644  push    rbp
0x140004645  push    rsi
0x140004646  push    rdi
0x140004647  push    r12
0x140004649  push    r13
0x14000464b  push    r14
0x14000464d  push    r15
0x14000464f  sub     rsp, 0C8h
0x140004656  mov     rax, cs:__security_cookie
0x14000465d  xor     rax, rsp
0x140004660  mov     [rsp+108h+var_50], rax
0x140004668  mov     rax, [rcx+48h]
0x14000466c  lea     rdx, [r11-88h]
0x140004673  mov     r15, [rsp+108h+arg_28]
0x14000467b  mov     r13, rcx
0x14000467e  mov     r14, [rsp+108h+arg_20]
0x140004686  xorps   xmm1, xmm1
0x140004689  xorps   xmm0, xmm0
0x14000468c  mov     [rsp+108h+var_C8], r8b
0x140004691  mov     rcx, [rax+28h]
0x140004695  lea     r8, [rsp+108h+String1]
0x14000469a  xor     eax, eax
0x14000469c  mov     [rsp+108h+var_B0], r14
0x1400046a1  mov     [rsp+108h+var_B8], rax
0x1400046a6  mov     ebp, r9d
0x1400046a9  mov     [r11-58h], rax
0x1400046ad  lea     r9, [rsp+108h+var_98]
0x1400046b2  mov     rdi, [rcx+28h]
0x1400046b6  mov     esi, 0C0000016h
0x1400046bb  mov     eax, [r15]
0x1400046be  mov     dword ptr [rsp+108h+var_C4], eax
0x1400046c2  mov     rax, [r13+38h]
0x1400046c6  mov     rbx, [rdi+1A8h]
0x1400046cd  movups  [rsp+108h+var_88], xmm0
0x1400046d5  lea     r10, [rax+168h]
0x1400046dc  movups  xmmword ptr [rsp+108h+String1.Length], xmm1
0x1400046e1  mov     qword ptr [rsp+108h+var_C4+4], r10
0x1400046e6  movups  [rsp+108h+var_98], xmm0
0x1400046eb  movzx   ecx, byte ptr [rax+163h]
0x1400046f2  and     cl, 3Ch
0x1400046f5  cmp     cl, 0Ch
0x1400046f8  mov     rcx, r10
0x1400046fb  movups  xmmword ptr [r11-78h], xmm1
0x140004700  setnz   r12b
0x140004704  movups  xmmword ptr [r11-68h], xmm1
0x140004709  call    cs:__imp_RxCrackPathName
0x140004710  nop     dword ptr [rax+rax+00h]
0x140004715  cmp     [rsp+108h+String1.Length], 0
0x14000471b  jz      loc_14000485D
0x140004721  cmp     word ptr [rsp+108h+var_98], 0
0x140004727  jnz     loc_14000485D
0x14000472d  lea     rdx, [rbx+458h]
0x140004734  cmp     ebp, 23h ; '#'
0x140004737  jz      loc_14000488B
0x14000473d  xor     eax, eax
0x14000473f  lea     r8, [rsp+108h+var_88]
0x140004747  mov     [rsp+108h+var_E0], rax
0x14000474c  xor     r9d, r9d
0x14000474f  mov     rcx, r13
0x140004752  mov     [rsp+108h+var_E8], rax
0x140004757  call    Smb2FindOrCreateDirCacheObject
0x14000475c  mov     rbx, rax
0x14000475f  test    rax, rax
0x140004762  jz      loc_14000483B
0x140004768  cmp     dword ptr [rax+20h], 0
0x14000476c  jnz     loc_14000483B
0x140004772  or      r12b, [rsp+108h+var_C8]
0x140004777  lock inc qword ptr [rdi+220h]
0x14000477f  xor     edx, edx
0x140004781  lea     rcx, [rax+68h]
0x140004785  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000478c  nop     dword ptr [rax+rax+00h]
0x140004791  lea     rax, [rsp+108h+var_C4]
0x140004796  mov     r9d, 4
0x14000479c  mov     [rsp+108h+var_D8], rax; __int64
0x1400047a1  lea     rdx, [rsp+108h+String1]; String1
0x1400047a6  cmp     ebp, 23h ; '#'
0x1400047a9  mov     [rsp+108h+var_E0], r14; __int64
0x1400047ae  movzx   r8d, r12b
0x1400047b2  mov     [rsp+108h+var_E8], 0; __int64
0x1400047bb  cmovnz  r9d, ebp
0x1400047bf  mov     rcx, rbx; Context
0x1400047c2  call    QueryFileInfoFromDirectoryCache
0x1400047c7  xor     edx, edx
0x1400047c9  lea     rcx, [rbx+68h]
0x1400047cd  mov     esi, eax
0x1400047cf  call    cs:__imp_ExReleasePushLockEx
0x1400047d6  nop     dword ptr [rax+rax+00h]
0x1400047db  cmp     esi, 0C0000225h
0x1400047e1  jz      loc_140004884
0x1400047e7  cmp     esi, 0C0000123h
0x1400047ed  jz      loc_140004884
0x1400047f3  cmp     esi, 0C0000003h
0x1400047f9  jz      loc_140004884
0x1400047ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140004806  lea     rax, WPP_GLOBAL_Control
0x14000480d  cmp     rcx, rax
0x140004810  jz      short loc_14000481F
0x140004812  test    dword ptr [rcx+2Ch], 100h
0x140004819  jnz     loc_1400048A0
0x14000481f  mov     rdi, qword ptr [rsp+108h+var_C4+4]
0x140004824  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 2
0x14000482b  jnz     loc_1400048CD
0x140004831  mov     rcx, [rsp+108h+var_58]
0x140004839  jmp     short loc_140004840
0x14000483b  mov     rcx, [rsp+108h+var_B8]
0x140004840  cmp     ebp, 23h ; '#'
0x140004843  jz      loc_140004909
0x140004849  mov     eax, dword ptr [rsp+108h+var_C4]
0x14000484d  mov     [r15], eax
0x140004850  test    rbx, rbx
0x140004853  jz      short loc_14000485D
0x140004855  mov     rcx, rbx; P
0x140004858  call    Smb2DereferenceDirCacheObject
0x14000485d  mov     eax, esi
0x14000485f  mov     rcx, [rsp+108h+var_50]
0x140004867  xor     rcx, rsp; StackCookie
0x14000486a  call    __security_check_cookie
0x14000486f  add     rsp, 0C8h
0x140004876  pop     r15
0x140004878  pop     r14
0x14000487a  pop     r13
0x14000487c  pop     r12
0x14000487e  pop     rdi
0x14000487f  pop     rsi
0x140004880  pop     rbp
0x140004881  pop     rbx
0x140004882  retn
0x140004884  mov     esi, 0C0000016h
0x140004889  jmp     short loc_140004855
0x14000488b  lea     r14, [rsp+108h+var_78]
0x140004893  mov     dword ptr [rsp+108h+var_C4], 28h ; '('
0x14000489b  jmp     loc_14000473D
0x1400048a0  cmp     byte ptr [rcx+29h], 2
0x1400048a4  mov     rdi, qword ptr [rsp+108h+var_C4+4]
0x1400048a9  jb      loc_140004824
0x1400048af  mov     rcx, [rcx+18h]
0x1400048b3  mov     r9, rbx
0x1400048b6  mov     dword ptr [rsp+108h+var_D8], esi
0x1400048ba  mov     [rsp+108h+var_E0], rdi
0x1400048bf  mov     dword ptr [rsp+108h+var_E8], ebp
0x1400048c3  call    WPP_SF_qdZD
0x1400048c8  jmp     loc_140004824
0x1400048cd  mov     rax, [rdi+8]
0x1400048d1  lea     r8, [r13+19Ch]
0x1400048d8  movzx   ecx, word ptr [rdi]
0x1400048db  lea     rdx, SmbFetchDirCache
0x1400048e2  mov     [rsp+108h+var_D0], esi
0x1400048e6  mov     r9, r13
0x1400048e9  mov     [rsp+108h+var_D8], rax
0x1400048ee  mov     rax, [r13+38h]
0x1400048f2  shr     cx, 1
0x1400048f5  mov     word ptr [rsp+108h+var_E0], cx
0x1400048fa  mov     [rsp+108h+var_E8], rax
0x1400048ff  call    McTemplateK0pphzr2q_EtwWriteTransfer
0x140004904  jmp     loc_140004831
0x140004909  test    esi, esi
0x14000490b  jnz     loc_1400383EC
0x140004911  bt      ecx, 0Ah
0x140004915  jb      loc_1400383EC
0x14000491b  cmp     dword ptr [r15], 8
0x14000491f  jb      loc_1400383E2
0x140004925  mov     rax, [rsp+108h+var_B0]
0x14000492a  mov     [rax], ecx
0x14000492c  mov     [rax+4], esi
0x14000492f  add     dword ptr [r15], 0FFFFFFF8h
0x140004933  jmp     loc_140004850
0x1400383e2  mov     esi, 0C0000023h
0x1400383e7  jmp     loc_140004850
0x1400383ec  mov     esi, 0C0000016h
0x1400383f1  jmp     loc_140004850
```
