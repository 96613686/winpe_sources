# CWMWriter::AddNextPin(uint,ulong,IWMStreamConfig *)

- ea: `0x18000e444`
- end: `0x18000e8bc`
- name: `?AddNextPin@CWMWriter@@AEAAJIKPEAUIWMStreamConfig@@@Z`
- size: `1144`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, unsigned int, unsigned int, struct IWMStreamConfig *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18000ea00`

## callees

- `0x180001020`
- `0x180001460`
- `0x180006f48`
- `0x180007004`
- `0x18000e444`
- `0x180013354`
- `0x180015218`
- `0x18001f010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e482`
- `KERNEL32!EnterCriticalSection` at `0x18000e482`
- `KERNEL32!LeaveCriticalSection` at `0x18000e4bc`
- `KERNEL32!LeaveCriticalSection` at `0x18000e88c`
- `KERNEL32!LeaveCriticalSection` at `0x18000e4bc`
- `KERNEL32!LeaveCriticalSection` at `0x18000e88c`

## pseudocode

```c
__int64 __fastcall CWMWriter::AddNextPin(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        unsigned int a3,
        struct IWMStreamConfig *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v8; // rax
  const wchar_t *v9; // r8
  __int64 v10; // rcx
  unsigned __int16 *v11; // rdx
  bool v12; // zf
  LONG RecursionCount; // ecx
  __int64 v14; // rax
  const wchar_t *v15; // r8
  __int64 v16; // rcx
  unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // rax
  int v19; // ecx
  __int64 v20; // rax
  const wchar_t *v21; // r8
  __int64 v22; // rcx
  unsigned __int16 *v23; // rdx
  unsigned __int16 *v24; // rax
  int v25; // ecx
  __int64 v26; // rax
  const wchar_t *v27; // r8
  __int64 v28; // rcx
  unsigned __int16 *v29; // rdx
  unsigned __int16 *v30; // rax
  int v31; // ecx
  __int64 v32; // rax
  const wchar_t *v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rax
  const wchar_t *v36; // r8
  __int64 v37; // rcx
  unsigned __int16 *v38; // rax
  int v39; // ecx
  int v40; // r13d
  CWMWriterInputPin *v41; // rax
  CWMWriterInputPin *v42; // r12
  CWMWriterInputPin *v43; // rax
  LONG *p_LockCount; // r15
  CWMWriterInputPin *v45; // rax
  int v46; // [rsp+40h] [rbp-39h] BYREF
  struct IWMStreamConfig *v47; // [rsp+48h] [rbp-31h]
  unsigned __int16 Src[12]; // [rsp+50h] [rbp-29h] BYREF
  __int16 v49; // [rsp+68h] [rbp-11h]
  __int16 v50; // [rsp+6Ah] [rbp-Fh]
  __int16 v51; // [rsp+6Ch] [rbp-Dh]
  __int16 v52; // [rsp+78h] [rbp-1h]
  __int16 v53; // [rsp+7Ah] [rbp+1h]

  v4 = this + 6;
  v47 = a4;
  EnterCriticalSection(this + 6);
  switch ( a3 )
  {
    case 1u:
      v35 = 2147483646;
      v36 = L"Audio Input 00";
      v37 = 30;
      v11 = Src;
      do
      {
        if ( !v35 )
          break;
        if ( !*v36 )
          break;
        *v11++ = *v36++;
        --v35;
        --v37;
      }
      while ( v37 );
      v12 = v37 == 0;
      RecursionCount = this[12].RecursionCount;
LABEL_44:
      v38 = v11 - 1;
      if ( !v12 )
        v38 = v11;
      v39 = RecursionCount + 1;
      *v38 = 0;
      v49 = v39 / 10 + 48;
      v50 = v39 % 10 + 48;
      break;
    case 2u:
      v32 = 2147483646;
      v33 = L"Video Input 00";
      v34 = 30;
      v11 = Src;
      do
      {
        if ( !v32 )
          break;
        if ( !*v33 )
          break;
        *v11++ = *v33++;
        --v32;
        --v34;
      }
      while ( v34 );
      v12 = v34 == 0;
      RecursionCount = (LONG)this[12].OwningThread;
      goto LABEL_44;
    case 3u:
      v26 = 2147483646;
      v27 = L"File Transfer Input 00";
      v28 = 30;
      v29 = Src;
      do
      {
        if ( !v26 )
          break;
        if ( !*v27 )
          break;
        *v29++ = *v27++;
        --v26;
        --v28;
      }
      while ( v28 );
      v30 = v29 - 1;
      if ( v28 )
        v30 = v29;
      v31 = HIDWORD(this[12].OwningThread) + 1;
      *v30 = 0;
      v52 = v31 / 10 + 48;
      v53 = v31 % 10 + 48;
      break;
    case 4u:
      v20 = 2147483646;
      v21 = L"Script Input 00";
      v22 = 30;
      v23 = Src;
      do
      {
        if ( !v20 )
          break;
        if ( !*v21 )
          break;
        *v23++ = *v21++;
        --v20;
        --v22;
      }
      while ( v22 );
      v24 = v23 - 1;
      if ( v22 )
        v24 = v23;
      v25 = LODWORD(this[12].LockSemaphore) + 1;
      *v24 = 0;
      v50 = v25 / 10 + 48;
      v51 = v25 % 10 + 48;
      break;
    case 5u:
      v14 = 2147483646;
      v15 = L"Text Input 00";
      v16 = 30;
      v17 = Src;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *v17++ = *v15++;
        --v14;
        --v16;
      }
      while ( v16 );
      v18 = v17 - 1;
      if ( v16 )
        v18 = v17;
      v19 = LODWORD(this[12].SpinCount) + 1;
      *v18 = 0;
      Src[11] = v19 / 10 + 48;
      v49 = v19 % 10 + 48;
      break;
    case 6u:
      v8 = 2147483646;
      v9 = L"Image Input 00";
      v10 = 30;
      v11 = Src;
      do
      {
        if ( !v8 )
          break;
        if ( !*v9 )
          break;
        *v11++ = *v9++;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = v10 == 0;
      RecursionCount = HIDWORD(this[12].LockSemaphore);
      goto LABEL_44;
    default:
      LeaveCriticalSection(v4);
      return 2147500037LL;
  }
  v46 = 0;
  v40 = 0;
  v41 = (CWMWriterInputPin *)CBaseList::RemoveI(
                               (CBaseList *)&this[11].LockCount,
                               *(struct __POSITION **)&this[11].LockCount);
  v42 = v41;
  if ( v41 )
  {
    p_LockCount = &this[12].LockCount;
    CWMWriterInputPin::Update(v41, Src, this[12].LockCount, a3, v47);
  }
  else
  {
    v43 = (CWMWriterInputPin *)operator new(0x210u);
    if ( !v43
      || (p_LockCount = &this[12].LockCount,
          v45 = CWMWriterInputPin::CWMWriterInputPin(
                  v43,
                  (struct CWMWriter *)this,
                  &v46,
                  Src,
                  this[12].LockCount,
                  a3,
                  v47),
          (v42 = v45) == 0) )
    {
      v40 = -2147024882;
      goto LABEL_66;
    }
    v40 = v46;
    if ( v46 >= 0 )
      goto LABEL_55;
    (*(void (__fastcall **)(CWMWriterInputPin *, __int64))(*(_QWORD *)v45 + 24LL))(v45, 1);
    v42 = 0;
  }
  if ( v40 >= 0 )
  {
LABEL_55:
    CBaseList::AddTailI((CBaseList *)&this[10].LockCount, v42);
    ++*p_LockCount;
    switch ( a3 )
    {
      case 1u:
        ++this[12].RecursionCount;
        break;
      case 2u:
        ++LODWORD(this[12].OwningThread);
        break;
      case 3u:
        ++HIDWORD(this[12].OwningThread);
        break;
      case 4u:
        ++LODWORD(this[12].LockSemaphore);
        break;
      case 5u:
        ++LODWORD(this[12].SpinCount);
        break;
      default:
        ++HIDWORD(this[12].LockSemaphore);
        break;
    }
  }
LABEL_66:
  LeaveCriticalSection(v4);
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x18000e444  mov     [rsp-8+arg_8], rbx
0x18000e449  push    rbp
0x18000e44a  push    rsi
0x18000e44b  push    rdi
0x18000e44c  push    r12
0x18000e44e  push    r13
0x18000e450  push    r14
0x18000e452  push    r15
0x18000e454  lea     rbp, [rsp-27h]
0x18000e459  sub     rsp, 0A0h
0x18000e460  mov     rax, cs:__security_cookie
0x18000e467  xor     rax, rsp
0x18000e46a  mov     [rbp+57h+var_40], rax
0x18000e46e  lea     rbx, [rcx+0F0h]
0x18000e475  mov     [rbp+57h+var_88], r9
0x18000e479  mov     rsi, rcx
0x18000e47c  mov     r14d, r8d
0x18000e47f  mov     rcx, rbx; lpCriticalSection
0x18000e482  call    cs:__imp_EnterCriticalSection
0x18000e488  mov     eax, r14d
0x18000e48b  sub     eax, 1
0x18000e48e  jz      loc_18000E6ED
0x18000e494  sub     eax, 1
0x18000e497  jz      loc_18000E6A7
0x18000e49d  sub     eax, 1
0x18000e4a0  jz      loc_18000E621
0x18000e4a6  sub     eax, 1
0x18000e4a9  jz      loc_18000E59B
0x18000e4af  sub     eax, 1
0x18000e4b2  jz      short loc_18000E515
0x18000e4b4  cmp     eax, 1
0x18000e4b7  jz      short loc_18000E4CC
0x18000e4b9  mov     rcx, rbx; lpCriticalSection
0x18000e4bc  call    cs:__imp_LeaveCriticalSection
0x18000e4c2  mov     eax, 80004005h
0x18000e4c7  jmp     loc_18000E895
0x18000e4cc  mov     eax, 7FFFFFFEh
0x18000e4d1  lea     r8, aImageInput00; "Image Input 00"
0x18000e4d8  mov     ecx, 1Eh
0x18000e4dd  lea     rdx, [rbp+57h+Src]
0x18000e4e1  xor     edi, edi
0x18000e4e3  test    rax, rax
0x18000e4e6  jz      short loc_18000E507
0x18000e4e8  movzx   r9d, word ptr [r8]
0x18000e4ec  test    r9w, r9w
0x18000e4f0  jz      short loc_18000E507
0x18000e4f2  mov     [rdx], r9w
0x18000e4f6  add     r8, 2
0x18000e4fa  add     rdx, 2
0x18000e4fe  dec     rax
0x18000e501  sub     rcx, 1
0x18000e505  jnz     short loc_18000E4E3
0x18000e507  test    rcx, rcx
0x18000e50a  mov     ecx, [rsi+1FCh]
0x18000e510  jmp     loc_18000E731
0x18000e515  mov     eax, 7FFFFFFEh
0x18000e51a  lea     r8, aTextInput00; "Text Input 00"
0x18000e521  mov     ecx, 1Eh
0x18000e526  lea     rdx, [rbp+57h+Src]
0x18000e52a  xor     edi, edi
0x18000e52c  test    rax, rax
0x18000e52f  jz      short loc_18000E550
0x18000e531  movzx   r9d, word ptr [r8]
0x18000e535  test    r9w, r9w
0x18000e539  jz      short loc_18000E550
0x18000e53b  mov     [rdx], r9w
0x18000e53f  add     r8, 2
0x18000e543  add     rdx, 2
0x18000e547  dec     rax
0x18000e54a  sub     rcx, 1
0x18000e54e  jnz     short loc_18000E52C
0x18000e550  test    rcx, rcx
0x18000e553  lea     rax, [rdx-2]
0x18000e557  mov     ecx, [rsi+200h]
0x18000e55d  cmovnz  rax, rdx
0x18000e561  inc     ecx
0x18000e563  mov     [rax], di
0x18000e566  mov     eax, 66666667h
0x18000e56b  imul    ecx
0x18000e56d  sar     edx, 2
0x18000e570  mov     eax, edx
0x18000e572  shr     eax, 1Fh
0x18000e575  add     edx, eax
0x18000e577  lea     eax, [rdx+30h]
0x18000e57a  mov     [rbp+57h+var_6A], ax
0x18000e57e  movzx   eax, dx
0x18000e581  shl     dx, 2
0x18000e585  add     ax, dx
0x18000e588  add     ax, ax
0x18000e58b  sub     cx, ax
0x18000e58e  add     cx, 30h ; '0'
0x18000e592  mov     [rbp+57h+var_68], cx
0x18000e596  jmp     loc_18000E76E
0x18000e59b  mov     eax, 7FFFFFFEh
0x18000e5a0  lea     r8, aScriptInput00; "Script Input 00"
0x18000e5a7  mov     ecx, 1Eh
0x18000e5ac  lea     rdx, [rbp+57h+Src]
0x18000e5b0  xor     edi, edi
0x18000e5b2  test    rax, rax
0x18000e5b5  jz      short loc_18000E5D6
0x18000e5b7  movzx   r9d, word ptr [r8]
0x18000e5bb  test    r9w, r9w
0x18000e5bf  jz      short loc_18000E5D6
0x18000e5c1  mov     [rdx], r9w
0x18000e5c5  add     r8, 2
0x18000e5c9  add     rdx, 2
0x18000e5cd  dec     rax
0x18000e5d0  sub     rcx, 1
0x18000e5d4  jnz     short loc_18000E5B2
0x18000e5d6  test    rcx, rcx
0x18000e5d9  lea     rax, [rdx-2]
0x18000e5dd  mov     ecx, [rsi+1F8h]
0x18000e5e3  cmovnz  rax, rdx
0x18000e5e7  inc     ecx
0x18000e5e9  mov     [rax], di
0x18000e5ec  mov     eax, 66666667h
0x18000e5f1  imul    ecx
0x18000e5f3  sar     edx, 2
0x18000e5f6  mov     eax, edx
0x18000e5f8  shr     eax, 1Fh
0x18000e5fb  add     edx, eax
0x18000e5fd  lea     eax, [rdx+30h]
0x18000e600  mov     [rbp+57h+var_66], ax
0x18000e604  movzx   eax, dx
0x18000e607  shl     dx, 2
0x18000e60b  add     ax, dx
0x18000e60e  add     ax, ax
0x18000e611  sub     cx, ax
0x18000e614  add     cx, 30h ; '0'
0x18000e618  mov     [rbp+57h+var_64], cx
0x18000e61c  jmp     loc_18000E76E
0x18000e621  mov     eax, 7FFFFFFEh
0x18000e626  lea     r8, aFileTransferIn; "File Transfer Input 00"
0x18000e62d  mov     ecx, 1Eh
0x18000e632  lea     rdx, [rbp+57h+Src]
0x18000e636  xor     edi, edi
0x18000e638  test    rax, rax
0x18000e63b  jz      short loc_18000E65C
0x18000e63d  movzx   r9d, word ptr [r8]
0x18000e641  test    r9w, r9w
0x18000e645  jz      short loc_18000E65C
0x18000e647  mov     [rdx], r9w
0x18000e64b  add     r8, 2
0x18000e64f  add     rdx, 2
0x18000e653  dec     rax
0x18000e656  sub     rcx, 1
0x18000e65a  jnz     short loc_18000E638
0x18000e65c  test    rcx, rcx
0x18000e65f  lea     rax, [rdx-2]
0x18000e663  mov     ecx, [rsi+1F4h]
0x18000e669  cmovnz  rax, rdx
0x18000e66d  inc     ecx
0x18000e66f  mov     [rax], di
0x18000e672  mov     eax, 66666667h
0x18000e677  imul    ecx
0x18000e679  sar     edx, 2
0x18000e67c  mov     eax, edx
0x18000e67e  shr     eax, 1Fh
0x18000e681  add     edx, eax
0x18000e683  lea     eax, [rdx+30h]
0x18000e686  mov     [rbp+57h+var_58], ax
0x18000e68a  movzx   eax, dx
0x18000e68d  shl     dx, 2
0x18000e691  add     ax, dx
0x18000e694  add     ax, ax
0x18000e697  sub     cx, ax
0x18000e69a  add     cx, 30h ; '0'
0x18000e69e  mov     [rbp+57h+var_56], cx
0x18000e6a2  jmp     loc_18000E76E
0x18000e6a7  mov     eax, 7FFFFFFEh
0x18000e6ac  lea     r8, aVideoInput00; "Video Input 00"
0x18000e6b3  mov     ecx, 1Eh
0x18000e6b8  lea     rdx, [rbp+57h+Src]
0x18000e6bc  xor     edi, edi
0x18000e6be  test    rax, rax
0x18000e6c1  jz      short loc_18000E6E2
0x18000e6c3  movzx   r9d, word ptr [r8]
0x18000e6c7  test    r9w, r9w
0x18000e6cb  jz      short loc_18000E6E2
0x18000e6cd  mov     [rdx], r9w
0x18000e6d1  add     r8, 2
0x18000e6d5  add     rdx, 2
0x18000e6d9  dec     rax
0x18000e6dc  sub     rcx, 1
0x18000e6e0  jnz     short loc_18000E6BE
0x18000e6e2  test    rcx, rcx
0x18000e6e5  mov     ecx, [rsi+1F0h]
0x18000e6eb  jmp     short loc_18000E731
0x18000e6ed  mov     eax, 7FFFFFFEh
0x18000e6f2  lea     r8, aAudioInput00; "Audio Input 00"
0x18000e6f9  mov     ecx, 1Eh
0x18000e6fe  lea     rdx, [rbp+57h+Src]
0x18000e702  xor     edi, edi
0x18000e704  test    rax, rax
0x18000e707  jz      short loc_18000E728
0x18000e709  movzx   r9d, word ptr [r8]
0x18000e70d  test    r9w, r9w
0x18000e711  jz      short loc_18000E728
0x18000e713  mov     [rdx], r9w
0x18000e717  add     r8, 2
0x18000e71b  add     rdx, 2
0x18000e71f  dec     rax
0x18000e722  sub     rcx, 1
0x18000e726  jnz     short loc_18000E704
0x18000e728  test    rcx, rcx
0x18000e72b  mov     ecx, [rsi+1ECh]
0x18000e731  lea     rax, [rdx-2]
0x18000e735  cmovnz  rax, rdx
0x18000e739  inc     ecx
0x18000e73b  mov     [rax], di
0x18000e73e  mov     eax, 66666667h
0x18000e743  imul    ecx
0x18000e745  sar     edx, 2
0x18000e748  mov     eax, edx
0x18000e74a  shr     eax, 1Fh
0x18000e74d  add     edx, eax
0x18000e74f  lea     eax, [rdx+30h]
0x18000e752  mov     [rbp+57h+var_68], ax
0x18000e756  movzx   eax, dx
0x18000e759  shl     dx, 2
0x18000e75d  add     ax, dx
0x18000e760  add     ax, ax
0x18000e763  sub     cx, ax
0x18000e766  add     cx, 30h ; '0'
0x18000e76a  mov     [rbp+57h+var_66], cx
0x18000e76e  lea     rcx, [rsi+1C0h]; this
0x18000e775  mov     [rbp+57h+var_90], edi
0x18000e778  mov     rdx, [rcx]; struct __POSITION *
0x18000e77b  mov     r13d, edi
0x18000e77e  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000e783  mov     r12, rax
0x18000e786  test    rax, rax
0x18000e789  jnz     short loc_18000E7FE
0x18000e78b  mov     ecx, 210h; Size
0x18000e790  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e795  test    rax, rax
0x18000e798  jz      short loc_18000E7F3
0x18000e79a  mov     rcx, [rbp+57h+var_88]
0x18000e79e  lea     r15, [rsi+1E8h]
0x18000e7a5  mov     [rsp+0D0h+var_A0], rcx; struct IWMStreamConfig *
0x18000e7aa  lea     r9, [rbp+57h+Src]; unsigned __int16 *
0x18000e7ae  mov     ecx, [r15]
0x18000e7b1  lea     r8, [rbp+57h+var_90]; int *
0x18000e7b5  mov     [rsp+0D0h+var_A8], r14d; unsigned int
0x18000e7ba  mov     rdx, rsi; struct CWMWriter *
0x18000e7bd  mov     dword ptr [rsp+0D0h+var_B0], ecx; int
0x18000e7c1  mov     rcx, rax; this
0x18000e7c4  call    ??0CWMWriterInputPin@@QEAA@PEAVCWMWriter@@PEAJPEBGHKPEAUIWMStreamConfig@@@Z; CWMWriterInputPin::CWMWriterInputPin(CWMWriter *,long *,ushort const *,int,ulong,IWMStreamConfig *)
0x18000e7c9  mov     r12, rax
0x18000e7cc  test    rax, rax
0x18000e7cf  jz      short loc_18000E7F3
0x18000e7d1  mov     r13d, [rbp+57h+var_90]
0x18000e7d5  test    r13d, r13d
0x18000e7d8  jns     short loc_18000E825
0x18000e7da  mov     rax, [rax]
0x18000e7dd  mov     edx, 1
0x18000e7e2  mov     rcx, r12
0x18000e7e5  mov     rax, [rax+18h]
0x18000e7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ee  mov     r12, rdi
0x18000e7f1  jmp     short loc_18000E820
0x18000e7f3  mov     r13d, 8007000Eh
0x18000e7f9  jmp     loc_18000E889
0x18000e7fe  mov     rcx, [rbp+57h+var_88]
0x18000e802  lea     r15, [rsi+1E8h]
0x18000e809  mov     r8d, [r15]; int
0x18000e80c  lea     rdx, [rbp+57h+Src]; Src
0x18000e810  mov     [rsp+0D0h+var_B0], rcx; struct IWMStreamConfig *
0x18000e815  mov     r9d, r14d; unsigned int
0x18000e818  mov     rcx, rax; this
0x18000e81b  call    ?Update@CWMWriterInputPin@@QEAAJPEBGHKPEAUIWMStreamConfig@@@Z; CWMWriterInputPin::Update(ushort const *,int,ulong,IWMStreamConfig *)
0x18000e820  test    r13d, r13d
0x18000e823  js      short loc_18000E889
0x18000e825  lea     rcx, [rsi+198h]; this
0x18000e82c  mov     rdx, r12; void *
0x18000e82f  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x18000e834  inc     dword ptr [r15]
0x18000e837  cmp     r14d, 1
0x18000e83b  jnz     short loc_18000E845
0x18000e83d  inc     dword ptr [rsi+1ECh]
0x18000e843  jmp     short loc_18000E889
0x18000e845  cmp     r14d, 2
0x18000e849  jnz     short loc_18000E853
0x18000e84b  inc     dword ptr [rsi+1F0h]
0x18000e851  jmp     short loc_18000E889
0x18000e853  cmp     r14d, 3
0x18000e857  jnz     short loc_18000E861
0x18000e859  inc     dword ptr [rsi+1F4h]
0x18000e85f  jmp     short loc_18000E889
0x18000e861  cmp     r14d, 4
0x18000e865  jnz     short loc_18000E86F
0x18000e867  inc     dword ptr [rsi+1F8h]
0x18000e86d  jmp     short loc_18000E889
0x18000e86f  cmp     r14d, 5
0x18000e873  jnz     short loc_18000E87D
0x18000e875  inc     dword ptr [rsi+200h]
0x18000e87b  jmp     short loc_18000E889
0x18000e87d  cmp     r14d, 6
0x18000e881  jnz     short loc_18000E889
0x18000e883  inc     dword ptr [rsi+1FCh]
  ... truncated ...
```
