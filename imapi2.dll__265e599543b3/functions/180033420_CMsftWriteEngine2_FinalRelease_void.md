# CMsftWriteEngine2::FinalRelease(void)

- ea: `0x180033420`
- end: `0x1800336c5`
- name: `?FinalRelease@CMsftWriteEngine2@@QEAAXXZ`
- size: `677`
- prototype: `void __fastcall(CMsftWriteEngine2 *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180032680`

## callees

- `0x18000908c`
- `0x180014180`
- `0x180016778`
- `0x180028ad8`
- `0x180033420`
- `0x18004a010`

## import_xrefs

- `USER32!MsgWaitForMultipleObjects` at `0x1800334e5`
- `USER32!MsgWaitForMultipleObjects` at `0x1800335bb`
- `USER32!MsgWaitForMultipleObjects` at `0x1800334e5`
- `USER32!MsgWaitForMultipleObjects` at `0x1800335bb`
- `KERNEL32!SetEvent` at `0x18003347e`
- `KERNEL32!SetEvent` at `0x18003347e`
- `KERNEL32!GetLastError` at `0x180033516`
- `KERNEL32!GetLastError` at `0x1800335ec`
- `KERNEL32!GetLastError` at `0x180033516`
- `KERNEL32!GetLastError` at `0x1800335ec`

## pseudocode

```c
void __fastcall CMsftWriteEngine2::FinalRelease(HANDLE *this, void **a2)
{
  HANDLE v3; // rcx
  DWORD v4; // eax
  DWORD v5; // edi
  DWORD LastError; // eax
  void **v7; // rdx
  void **v8; // rdx
  DWORD v9; // eax
  DWORD v10; // edi
  DWORD v11; // eax
  void **v12; // rdx
  void **v13; // rdx
  void **v14; // rdx
  void **v15; // rdx
  void **v16; // rdx
  HANDLE v17; // rcx
  HANDLE v18; // rcx
  HANDLE v19; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 47, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, this);
  }
  v3 = this[24];
  if ( v3 )
    SetEvent(v3);
  if ( this[25] )
  {
    while ( 1 )
    {
      v4 = MsgWaitForMultipleObjects(1u, this + 25, 0, 0x2710u, 0);
      v5 = v4;
      if ( v4 != 258 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 48, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      }
    }
    if ( v4
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        49,
        WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
        v5,
        v5,
        LastError);
    }
  }
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 25), a2);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 26), v7);
  if ( this[28] )
  {
    while ( 1 )
    {
      v9 = MsgWaitForMultipleObjects(1u, this + 28, 0, 0x2710u, 0);
      v10 = v9;
      if ( v9 != 258 )
        break;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 50, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
      }
    }
    if ( v9
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
    {
      v11 = GetLastError();
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        51,
        WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids,
        v10,
        v10,
        v11);
    }
  }
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 28), v8);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 29), v12);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 24), v13);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 21), v14);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 22), v15);
  Imapi2Utility::CloseHandleAndNull((Imapi2Utility *)(this + 23), v16);
  v17 = this[16];
  if ( v17 )
  {
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v17 + 8LL))(v17);
    this[16] = 0;
  }
  v18 = this[15];
  if ( v18 )
  {
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v18 + 8LL))(v18);
    this[15] = 0;
  }
  v19 = this[14];
  if ( v19 )
  {
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v19 + 16LL))(v19);
    this[14] = 0;
  }
}

```

## disassembly

```asm
0x180033420  push    rbx
0x180033422  push    rsi
0x180033423  push    rdi
0x180033424  push    r12
0x180033426  push    r14
0x180033428  sub     rsp, 30h
0x18003342c  mov     rbx, rcx
0x18003342f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033436  lea     r12, WPP_GLOBAL_Control
0x18003343d  cmp     rcx, r12
0x180033440  jz      short loc_18003346F
0x180033442  test    byte ptr [rcx+0E4h], 2
0x180033449  jz      short loc_18003346F
0x18003344b  cmp     byte ptr [rcx+0E1h], 4
0x180033452  jb      short loc_18003346F
0x180033454  mov     rcx, [rcx+0D8h]
0x18003345b  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033462  mov     edx, 2Fh ; '/'
0x180033467  mov     r9, rbx
0x18003346a  call    WPP_SF_q
0x18003346f  lea     r14, [rbx+0C0h]
0x180033476  mov     rcx, [r14]; hEvent
0x180033479  test    rcx, rcx
0x18003347c  jz      short loc_180033484
0x18003347e  call    cs:__imp_SetEvent
0x180033484  lea     rsi, [rbx+0C8h]
0x18003348b  cmp     qword ptr [rsi], 0
0x18003348f  jz      loc_180033546
0x180033495  jmp     short loc_1800334CD
0x180033497  mov     rcx, cs:WPP_GLOBAL_Control
0x18003349e  cmp     rcx, r12
0x1800334a1  jz      short loc_1800334CD
0x1800334a3  test    byte ptr [rcx+0E4h], 4
0x1800334aa  jz      short loc_1800334CD
0x1800334ac  cmp     byte ptr [rcx+0E1h], 1
0x1800334b3  jb      short loc_1800334CD
0x1800334b5  mov     rcx, [rcx+0D8h]
0x1800334bc  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x1800334c3  mov     edx, 30h ; '0'
0x1800334c8  call    WPP_SF_
0x1800334cd  xor     r8d, r8d; fWaitAll
0x1800334d0  mov     [rsp+58h+dwWakeMask], 0; dwWakeMask
0x1800334d8  mov     r9d, 2710h; dwMilliseconds
0x1800334de  mov     rdx, rsi; pHandles
0x1800334e1  lea     ecx, [r8+1]; nCount
0x1800334e5  call    cs:__imp_MsgWaitForMultipleObjects
0x1800334eb  mov     edi, eax
0x1800334ed  cmp     eax, 102h
0x1800334f2  jz      short loc_180033497
0x1800334f4  test    eax, eax
0x1800334f6  jz      short loc_180033546
0x1800334f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800334ff  cmp     rax, r12
0x180033502  jz      short loc_180033546
0x180033504  test    byte ptr [rax+0E4h], 4
0x18003350b  jz      short loc_180033546
0x18003350d  cmp     byte ptr [rax+0E1h], 2
0x180033514  jb      short loc_180033546
0x180033516  call    cs:__imp_GetLastError
0x18003351c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033523  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x18003352a  mov     [rsp+58h+var_30], eax
0x18003352e  mov     edx, 31h ; '1'
0x180033533  mov     r9d, edi
0x180033536  mov     [rsp+58h+dwWakeMask], edi
0x18003353a  mov     rcx, [rcx+0D8h]
0x180033541  call    WPP_SF_ddD
0x180033546  mov     rcx, rsi; this
0x180033549  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x18003354e  lea     rcx, [rbx+0D0h]; this
0x180033555  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x18003355a  lea     rsi, [rbx+0E0h]
0x180033561  cmp     qword ptr [rsi], 0
0x180033565  jz      loc_18003361C
0x18003356b  jmp     short loc_1800335A3
0x18003356d  mov     rcx, cs:WPP_GLOBAL_Control
0x180033574  cmp     rcx, r12
0x180033577  jz      short loc_1800335A3
0x180033579  test    byte ptr [rcx+0E4h], 4
0x180033580  jz      short loc_1800335A3
0x180033582  cmp     byte ptr [rcx+0E1h], 1
0x180033589  jb      short loc_1800335A3
0x18003358b  mov     rcx, [rcx+0D8h]
0x180033592  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033599  mov     edx, 32h ; '2'
0x18003359e  call    WPP_SF_
0x1800335a3  xor     r8d, r8d; fWaitAll
0x1800335a6  mov     [rsp+58h+dwWakeMask], 0; dwWakeMask
0x1800335ae  mov     r9d, 2710h; dwMilliseconds
0x1800335b4  mov     rdx, rsi; pHandles
0x1800335b7  lea     ecx, [r8+1]; nCount
0x1800335bb  call    cs:__imp_MsgWaitForMultipleObjects
0x1800335c1  mov     edi, eax
0x1800335c3  cmp     eax, 102h
0x1800335c8  jz      short loc_18003356D
0x1800335ca  test    eax, eax
0x1800335cc  jz      short loc_18003361C
0x1800335ce  mov     rax, cs:WPP_GLOBAL_Control
0x1800335d5  cmp     rax, r12
0x1800335d8  jz      short loc_18003361C
0x1800335da  test    byte ptr [rax+0E4h], 4
0x1800335e1  jz      short loc_18003361C
0x1800335e3  cmp     byte ptr [rax+0E1h], 2
0x1800335ea  jb      short loc_18003361C
0x1800335ec  call    cs:__imp_GetLastError
0x1800335f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800335f9  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180033600  mov     [rsp+58h+var_30], eax
0x180033604  mov     edx, 33h ; '3'
0x180033609  mov     r9d, edi
0x18003360c  mov     [rsp+58h+dwWakeMask], edi
0x180033610  mov     rcx, [rcx+0D8h]
0x180033617  call    WPP_SF_ddD
0x18003361c  mov     rcx, rsi; this
0x18003361f  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180033624  lea     rcx, [rbx+0E8h]; this
0x18003362b  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180033630  mov     rcx, r14; this
0x180033633  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180033638  lea     rcx, [rbx+0A8h]; this
0x18003363f  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180033644  lea     rcx, [rbx+0B0h]; this
0x18003364b  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x180033650  lea     rcx, [rbx+0B8h]; this
0x180033657  call    ?CloseHandleAndNull@Imapi2Utility@@YAXAEAPEAX@Z; Imapi2Utility::CloseHandleAndNull(void * &)
0x18003365c  mov     rcx, [rbx+80h]
0x180033663  test    rcx, rcx
0x180033666  jz      short loc_18003367F
0x180033668  mov     rax, [rcx]
0x18003366b  mov     rax, [rax+8]
0x18003366f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033674  mov     qword ptr [rbx+80h], 0
0x18003367f  mov     rcx, [rbx+78h]
0x180033683  test    rcx, rcx
0x180033686  jz      short loc_18003369C
0x180033688  mov     rax, [rcx]
0x18003368b  mov     rax, [rax+8]
0x18003368f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033694  mov     qword ptr [rbx+78h], 0
0x18003369c  mov     rcx, [rbx+70h]
0x1800336a0  test    rcx, rcx
0x1800336a3  jz      short loc_1800336B9
0x1800336a5  mov     rax, [rcx]
0x1800336a8  mov     rax, [rax+10h]
0x1800336ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800336b1  mov     qword ptr [rbx+70h], 0
0x1800336b9  add     rsp, 30h
0x1800336bd  pop     r14
0x1800336bf  pop     r12
0x1800336c1  pop     rdi
0x1800336c2  pop     rsi
0x1800336c3  pop     rbx
0x1800336c4  retn
```
