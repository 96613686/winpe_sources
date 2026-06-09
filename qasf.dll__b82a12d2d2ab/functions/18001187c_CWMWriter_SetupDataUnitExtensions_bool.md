# CWMWriter::SetupDataUnitExtensions(bool *)

- ea: `0x18001187c`
- end: `0x1800119da`
- name: `?SetupDataUnitExtensions@CWMWriter@@IEAAJPEA_N@Z`
- size: `350`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000ea00`

## callees

- `0x180001460`
- `0x18001187c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::SetupDataUnitExtensions(CWMWriter *this, bool *a2)
{
  __int64 v2; // rsi
  unsigned int v3; // ebp
  bool v4; // bl
  __int64 v7; // rdi
  int (__fastcall ***v8)(_QWORD, GUID *, __int64 **); // rcx
  __int64 v9; // rax
  IID v11; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v12; // [rsp+40h] [rbp-38h] BYREF

  v2 = *((_QWORD *)this + 51);
  v3 = 0;
  v4 = 0;
  if ( v2 )
  {
    do
    {
      v7 = *(_QWORD *)(v2 + 16);
      v2 = *(_QWORD *)(v2 + 8);
      if ( v7 )
      {
        if ( *(_DWORD *)(v7 + 424) == 2 )
        {
          v8 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 **))(v7 + 448);
          *(_DWORD *)(v7 + 512) = 1;
          *(_DWORD *)(v7 + 516) = 1;
          if ( v8 )
          {
            v12 = 0;
            if ( (**v8)(v8, &IID_IWMStreamConfig2, &v12) >= 0 )
            {
              v9 = *v12;
              v11 = WM_SampleExtensionGUID_PixelAspectRatio;
              (*(void (__fastcall **)(__int64 *, IID *, __int64, _QWORD, _DWORD))(v9 + 128))(v12, &v11, 2, 0, 0);
              v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 112LL))(
                     *((_QWORD *)this + 43),
                     *(_QWORD *)(v7 + 448));
              (*(void (__fastcall **)(__int64 *))(*v12 + 16))(v12);
              v4 = 1;
              *(_DWORD *)(v7 + 508) = 1;
            }
          }
        }
      }
    }
    while ( v2 );
    if ( v4 )
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 39) + 32LL))(
             *((_QWORD *)this + 39),
             *((_QWORD *)this + 43));
  }
  *a2 = v4;
  return v3;
}

```

## disassembly

```asm
0x18001187c  mov     [rsp+arg_10], rbx
0x180011881  push    rbp
0x180011882  push    rsi
0x180011883  push    rdi
0x180011884  push    r14
0x180011886  push    r15
0x180011888  sub     rsp, 50h
0x18001188c  mov     rax, cs:__security_cookie
0x180011893  xor     rax, rsp
0x180011896  mov     [rsp+78h+var_30], rax
0x18001189b  mov     rsi, [rcx+198h]
0x1800118a2  xor     ebp, ebp
0x1800118a4  xor     bl, bl
0x1800118a6  mov     r15, rdx
0x1800118a9  mov     r14, rcx
0x1800118ac  test    rsi, rsi
0x1800118af  jz      loc_1800119B4
0x1800118b5  mov     rdi, [rsi+10h]
0x1800118b9  mov     rsi, [rsi+8]
0x1800118bd  test    rdi, rdi
0x1800118c0  jz      loc_18001198B
0x1800118c6  cmp     dword ptr [rdi+1A8h], 2
0x1800118cd  jnz     loc_18001198B
0x1800118d3  mov     rcx, [rdi+1C0h]
0x1800118da  mov     dword ptr [rdi+200h], 1
0x1800118e4  mov     dword ptr [rdi+204h], 1
0x1800118ee  test    rcx, rcx
0x1800118f1  jz      loc_18001198B
0x1800118f7  mov     [rsp+78h+var_38], 0
0x180011900  lea     r8, [rsp+78h+var_38]
0x180011905  mov     rax, [rcx]
0x180011908  lea     rdx, IID_IWMStreamConfig2
0x18001190f  mov     rax, [rax]
0x180011912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011917  test    eax, eax
0x180011919  js      short loc_18001198B
0x18001191b  mov     rcx, [rsp+78h+var_38]
0x180011920  lea     rdx, [rsp+78h+var_48]
0x180011925  movups  xmm0, xmmword ptr cs:WM_SampleExtensionGUID_PixelAspectRatio.Data1
0x18001192c  mov     r8d, 2
0x180011932  mov     [rsp+78h+var_58], 0
0x18001193a  xor     r9d, r9d
0x18001193d  mov     rax, [rcx]
0x180011940  movdqu  [rsp+78h+var_48], xmm0
0x180011946  mov     rax, [rax+80h]
0x18001194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011952  mov     rcx, [r14+158h]
0x180011959  mov     rdx, [rdi+1C0h]
0x180011960  mov     rax, [rcx]
0x180011963  mov     rax, [rax+70h]
0x180011967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196c  mov     rcx, [rsp+78h+var_38]
0x180011971  mov     ebp, eax
0x180011973  mov     rdx, [rcx]
0x180011976  mov     rax, [rdx+10h]
0x18001197a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001197f  mov     bl, 1
0x180011981  mov     dword ptr [rdi+1FCh], 1
0x18001198b  test    rsi, rsi
0x18001198e  jnz     loc_1800118B5
0x180011994  test    bl, bl
0x180011996  jz      short loc_1800119B4
0x180011998  mov     rcx, [r14+138h]
0x18001199f  mov     rdx, [r14+158h]
0x1800119a6  mov     rax, [rcx]
0x1800119a9  mov     rax, [rax+20h]
0x1800119ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119b2  mov     ebp, eax
0x1800119b4  mov     [r15], bl
0x1800119b7  mov     eax, ebp
0x1800119b9  mov     rcx, [rsp+78h+var_30]
0x1800119be  xor     rcx, rsp; StackCookie
0x1800119c1  call    __security_check_cookie
0x1800119c6  mov     rbx, [rsp+78h+arg_10]
0x1800119ce  add     rsp, 50h
0x1800119d2  pop     r15
0x1800119d4  pop     r14
0x1800119d6  pop     rdi
0x1800119d7  pop     rsi
0x1800119d8  pop     rbp
0x1800119d9  retn
```
