# DllMain

- ea: `0x18000b8f0`
- end: `0x18000ba3a`
- name: `DllMain`
- size: `330`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001654`

## callees

- `0x18000a3d0`
- `0x18000b8f0`
- `0x1800182a0`
- `0x180019010`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18000b916`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000b916`
- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x18000b99e`
- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x18000b99e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  _BOOL8 v3; // rdi
  __int64 v4; // rcx
  void (__fastcall **v5)(_QWORD); // rbx
  __int64 *v6; // rbx
  __int64 *v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  void (__fastcall *v10)(_QWORD); // rax
  __int64 *v11; // rbx
  __int64 *v12; // rax
  INITCOMMONCONTROLSEX picce; // [rsp+48h] [rbp+20h] BYREF

  LODWORD(v3) = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_hInst = hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
      v5 = (void (__fastcall **)(_QWORD))&off_180021000;
      if ( &off_180021000 != (_UNKNOWN *)-1LL )
      {
        qword_180021C48 = (__int64)&off_180021000;
        if ( off_180021000 )
        {
          do
          {
            LOBYTE(v4) = 1;
            v5[8](v4);
            v5 += 9;
          }
          while ( *v5 );
        }
      }
      v6 = off_1800212A0[0];
      v7 = off_1800212A8;
      while ( v6 < v7 )
      {
        if ( *v6 )
        {
          LOBYTE(v4) = 1;
          (*(void (__fastcall **)(__int64))(*v6 + 64))(v4);
          v7 = off_1800212A8;
        }
        ++v6;
      }
      picce.dwSize = 8;
      picce.dwICC = 255;
      InitCommonControlsEx(&picce);
      return LinkWindow_RegisterClass() != 0;
    }
  }
  else
  {
    v8 = (_QWORD *)qword_180021C48;
    if ( qword_180021C48 )
    {
      while ( *v8 )
      {
        v9 = v8[4];
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        v10 = (void (__fastcall *)(_QWORD))v8[8];
        v8[4] = 0;
        v10(0);
        v8 += 9;
      }
    }
    v11 = off_1800212A0[0];
    v12 = off_1800212A8;
    while ( v11 < v12 )
    {
      if ( *v11 )
      {
        (*(void (__fastcall **)(_QWORD))(*v11 + 64))(0);
        v12 = off_1800212A8;
      }
      ++v11;
    }
    ATL::CAtlModule::Term((ATL::CAtlModule *)&_Module);
  }
  return v3;
}

```

## disassembly

```asm
0x18000b8f0  mov     [rsp+arg_0], rbx
0x18000b8f5  push    rdi
0x18000b8f6  sub     rsp, 20h
0x18000b8fa  mov     edi, 1
0x18000b8ff  test    edx, edx
0x18000b901  jz      loc_18000B9AE
0x18000b907  cmp     edx, edi
0x18000b909  jnz     loc_18000BA2D
0x18000b90f  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x18000b916  call    cs:__imp_DisableThreadLibraryCalls
0x18000b91c  lea     rbx, off_180021000
0x18000b923  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b927  jz      short loc_18000B950
0x18000b929  cmp     cs:off_180021000, 0
0x18000b931  mov     cs:qword_180021C48, rbx
0x18000b938  jz      short loc_18000B950
0x18000b93a  mov     rax, [rbx+40h]
0x18000b93e  mov     cl, dil
0x18000b941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b946  lea     rbx, [rbx+48h]
0x18000b94a  cmp     qword ptr [rbx], 0
0x18000b94e  jnz     short loc_18000B93A
0x18000b950  mov     rbx, cs:off_1800212A0
0x18000b957  mov     rax, cs:off_1800212A8
0x18000b95e  jmp     short loc_18000B97F
0x18000b960  mov     rdx, [rbx]
0x18000b963  test    rdx, rdx
0x18000b966  jz      short loc_18000B97B
0x18000b968  mov     rax, [rdx+40h]
0x18000b96c  mov     cl, dil
0x18000b96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b974  mov     rax, cs:off_1800212A8
0x18000b97b  add     rbx, 8
0x18000b97f  cmp     rbx, rax
0x18000b982  jb      short loc_18000B960
0x18000b984  lea     rcx, [rsp+28h+picce]; picce
0x18000b989  mov     [rsp+28h+picce.dwSize], 8
0x18000b991  mov     [rsp+28h+picce.dwICC], 0FFh
0x18000b999  call    InitCommonControlsEx
0x18000b99e  call    cs:__imp_LinkWindow_RegisterClass
0x18000b9a4  xor     edi, edi
0x18000b9a6  test    eax, eax
0x18000b9a8  setnz   dil
0x18000b9ac  jmp     short loc_18000BA2D
0x18000b9ae  mov     rbx, cs:qword_180021C48
0x18000b9b5  test    rbx, rbx
0x18000b9b8  jz      short loc_18000B9EE
0x18000b9ba  jmp     short loc_18000B9E8
0x18000b9bc  mov     rcx, [rbx+20h]
0x18000b9c0  test    rcx, rcx
0x18000b9c3  jz      short loc_18000B9D1
0x18000b9c5  mov     rax, [rcx]
0x18000b9c8  mov     rax, [rax+10h]
0x18000b9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9d1  mov     rax, [rbx+40h]
0x18000b9d5  xor     ecx, ecx
0x18000b9d7  mov     qword ptr [rbx+20h], 0
0x18000b9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e4  add     rbx, 48h ; 'H'
0x18000b9e8  cmp     qword ptr [rbx], 0
0x18000b9ec  jnz     short loc_18000B9BC
0x18000b9ee  mov     rbx, cs:off_1800212A0
0x18000b9f5  mov     rax, cs:off_1800212A8
0x18000b9fc  jmp     short loc_18000BA1C
0x18000b9fe  mov     rdx, [rbx]
0x18000ba01  test    rdx, rdx
0x18000ba04  jz      short loc_18000BA18
0x18000ba06  mov     rax, [rdx+40h]
0x18000ba0a  xor     ecx, ecx
0x18000ba0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba11  mov     rax, cs:off_1800212A8
0x18000ba18  add     rbx, 8
0x18000ba1c  cmp     rbx, rax
0x18000ba1f  jb      short loc_18000B9FE
0x18000ba21  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x18000ba28  call    ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
0x18000ba2d  mov     rbx, [rsp+28h+arg_0]
0x18000ba32  mov     eax, edi
0x18000ba34  add     rsp, 20h
0x18000ba38  pop     rdi
0x18000ba39  retn
```
