# CMsftWriteEngine2::put_Recorder(IDiscRecorder2Ex *)

- ea: `0x180034750`
- end: `0x180034954`
- name: `?put_Recorder@CMsftWriteEngine2@@UEAAJPEAUIDiscRecorder2Ex@@@Z`
- size: `516`
- prototype: `int(CMsftWriteEngine2 *__hidden this, struct IDiscRecorder2Ex *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000fdd4`
- `0x1800140f4`
- `0x180016778`
- `0x180034750`
- `0x180034f30`
- `0x180035988`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::put_Recorder(CMsftWriteEngine2 *this, struct IDiscRecorder2Ex *a2)
{
  DWORD v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  CWriteEngineStaticDriveInformation *v7; // rax
  CWriteEngineStaticDriveInformation *v8; // rax
  CWriteEngineStaticDriveInformation *v9; // rsi
  const struct _GUID *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx

  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 30, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
    }
    return (DWORD)-2147467261;
  }
  if ( *((_WORD *)this + 122) )
  {
    v4 = -2147467259;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
    {
      return v4;
    }
    v6 = 31;
    goto LABEL_33;
  }
  v7 = (CWriteEngineStaticDriveInformation *)operator new(0x30u);
  if ( !v7 || (v8 = CWriteEngineStaticDriveInformation::CWriteEngineStaticDriveInformation(v7), (v9 = v8) == 0) )
  {
    v4 = -2147024882;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 225) < 3u )
    {
      return v4;
    }
    v6 = 32;
LABEL_33:
    WPP_SF_(v5[27], v6, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids);
    return v4;
  }
  v4 = CWriteEngineStaticDriveInformation::Init(v8, a2);
  if ( (v4 & 0x80000000) == 0 )
  {
    v11 = *((_QWORD *)this + 14);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *((_QWORD *)this + 14) = 0;
    }
    v12 = *((_QWORD *)this + 15);
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      *((_QWORD *)this + 15) = 0;
    }
    v13 = *((_QWORD *)this + 16);
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      *((_QWORD *)this + 16) = 0;
    }
    ((void (__fastcall *)(struct IDiscRecorder2Ex *))a2->lpVtbl->AddRef)(a2);
    *((_QWORD *)this + 14) = a2;
    *((_QWORD *)this + 15) = v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids, v4);
    }
    (*(void (__fastcall **)(CWriteEngineStaticDriveInformation *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  if ( (v4 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v4, (__int64)&CLSID_MsftWriteEngine2, v10);
  return v4;
}

```

## disassembly

```asm
0x180034750  push    rbx
0x180034752  push    rbp
0x180034753  push    rsi
0x180034754  push    rdi
0x180034755  push    r14
0x180034757  sub     rsp, 20h
0x18003475b  xor     ebp, ebp
0x18003475d  mov     r14, rdx
0x180034760  mov     rdi, rcx
0x180034763  test    rdx, rdx
0x180034766  jnz     short loc_1800347AD
0x180034768  mov     rcx, cs:WPP_GLOBAL_Control
0x18003476f  lea     rax, WPP_GLOBAL_Control
0x180034776  cmp     rcx, rax
0x180034779  jz      short loc_1800347A3
0x18003477b  test    byte ptr [rcx+0E4h], 4
0x180034782  jz      short loc_1800347A3
0x180034784  cmp     byte ptr [rcx+0E1h], 3
0x18003478b  jb      short loc_1800347A3
0x18003478d  mov     rcx, [rcx+0D8h]
0x180034794  lea     edx, [rbp+1Eh]
0x180034797  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x18003479e  call    WPP_SF_
0x1800347a3  mov     ebx, 80004003h
0x1800347a8  jmp     loc_180034947
0x1800347ad  cmp     [rcx+0F4h], bp
0x1800347b4  jz      short loc_1800347F6
0x1800347b6  mov     ebx, 80004005h
0x1800347bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800347c2  lea     rax, WPP_GLOBAL_Control
0x1800347c9  cmp     rcx, rax
0x1800347cc  jz      loc_180034947
0x1800347d2  test    byte ptr [rcx+0E4h], 4
0x1800347d9  jz      loc_180034947
0x1800347df  cmp     byte ptr [rcx+0E1h], 3
0x1800347e6  jb      loc_180034947
0x1800347ec  mov     edx, 1Fh
0x1800347f1  jmp     loc_180034934
0x1800347f6  mov     ecx, 30h ; '0'; Size
0x1800347fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034800  test    rax, rax
0x180034803  jz      loc_180034905
0x180034809  mov     rcx, rax; this
0x18003480c  call    ??0CWriteEngineStaticDriveInformation@@QEAA@XZ; CWriteEngineStaticDriveInformation::CWriteEngineStaticDriveInformation(void)
0x180034811  mov     rsi, rax
0x180034814  test    rax, rax
0x180034817  jz      loc_180034905
0x18003481d  mov     rdx, r14; struct IDiscRecorder2Ex *
0x180034820  mov     rcx, rax; this
0x180034823  call    ?Init@CWriteEngineStaticDriveInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CWriteEngineStaticDriveInformation::Init(IDiscRecorder2Ex *)
0x180034828  mov     ebx, eax
0x18003482a  test    eax, eax
0x18003482c  jns     short loc_18003487F
0x18003482e  mov     rcx, cs:WPP_GLOBAL_Control
0x180034835  lea     rax, WPP_GLOBAL_Control
0x18003483c  cmp     rcx, rax
0x18003483f  jz      short loc_18003486E
0x180034841  test    byte ptr [rcx+0E4h], 4
0x180034848  jz      short loc_18003486E
0x18003484a  cmp     byte ptr [rcx+0E1h], 3
0x180034851  jb      short loc_18003486E
0x180034853  mov     rcx, [rcx+0D8h]
0x18003485a  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180034861  mov     edx, 21h ; '!'
0x180034866  mov     r9d, ebx
0x180034869  call    WPP_SF_d
0x18003486e  mov     rax, [rsi]
0x180034871  mov     rcx, rsi
0x180034874  mov     rax, [rax+8]
0x180034878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003487d  jmp     short loc_1800348E7
0x18003487f  mov     rcx, [rdi+70h]
0x180034883  test    rcx, rcx
0x180034886  jz      short loc_180034898
0x180034888  mov     rax, [rcx]
0x18003488b  mov     rax, [rax+10h]
0x18003488f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034894  mov     [rdi+70h], rbp
0x180034898  mov     rcx, [rdi+78h]
0x18003489c  test    rcx, rcx
0x18003489f  jz      short loc_1800348B1
0x1800348a1  mov     rax, [rcx]
0x1800348a4  mov     rax, [rax+8]
0x1800348a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348ad  mov     [rdi+78h], rbp
0x1800348b1  mov     rcx, [rdi+80h]
0x1800348b8  test    rcx, rcx
0x1800348bb  jz      short loc_1800348D0
0x1800348bd  mov     rax, [rcx]
0x1800348c0  mov     rax, [rax+8]
0x1800348c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348c9  mov     [rdi+80h], rbp
0x1800348d0  mov     rax, [r14]
0x1800348d3  mov     rcx, r14
0x1800348d6  mov     rax, [rax+8]
0x1800348da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348df  mov     [rdi+70h], r14
0x1800348e3  mov     [rdi+78h], rsi
0x1800348e7  mov     eax, ebx
0x1800348e9  and     eax, 80FF0000h
0x1800348ee  cmp     eax, 80AA0000h
0x1800348f3  jnz     short loc_180034947
0x1800348f5  lea     rdx, CLSID_MsftWriteEngine2; int
0x1800348fc  mov     ecx, ebx; dwMessageId
0x1800348fe  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180034903  jmp     short loc_180034947
0x180034905  mov     ebx, 8007000Eh
0x18003490a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034911  lea     rax, WPP_GLOBAL_Control
0x180034918  cmp     rcx, rax
0x18003491b  jz      short loc_180034947
0x18003491d  test    byte ptr [rcx+0E4h], 4
0x180034924  jz      short loc_180034947
0x180034926  cmp     byte ptr [rcx+0E1h], 3
0x18003492d  jb      short loc_180034947
0x18003492f  mov     edx, 20h ; ' '
0x180034934  mov     rcx, [rcx+0D8h]
0x18003493b  lea     r8, WPP_46aa905702f9300c53a77f37c30f4ded_Traceguids
0x180034942  call    WPP_SF_
0x180034947  mov     eax, ebx
0x180034949  add     rsp, 20h
0x18003494d  pop     r14
0x18003494f  pop     rdi
0x180034950  pop     rsi
0x180034951  pop     rbp
0x180034952  pop     rbx
0x180034953  retn
```
