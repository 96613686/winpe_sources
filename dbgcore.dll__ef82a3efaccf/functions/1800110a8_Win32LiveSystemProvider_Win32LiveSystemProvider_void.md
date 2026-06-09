# Win32LiveSystemProvider::~Win32LiveSystemProvider(void)

- ea: `0x1800110a8`
- end: `0x18001135a`
- name: `??1Win32LiveSystemProvider@@UEAA@XZ`
- size: `690`
- prototype: `void __fastcall(Win32LiveSystemProvider *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800113a4`
- `0x180023234`

## callees

- `0x1800110a8`
- `0x180026dac`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800110de`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800110f4`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001110d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011126`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001113c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011152`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001116b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011184`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001119d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800111b6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800111cf`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800111e8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011201`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001121a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011233`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001124c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011265`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001127e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011297`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112b0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112c9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112e2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112fb`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800110de`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800110f4`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001110d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011126`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001113c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011152`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001116b`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011184`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001119d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800111b6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800111cf`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800111e8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011201`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001121a`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011233`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001124c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011265`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001127e`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180011297`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112b0`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112c9`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112e2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800112fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001131b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001131b`

## pseudocode

```c
void __fastcall Win32LiveSystemProvider::~Win32LiveSystemProvider(Win32LiveSystemProvider *this)
{
  HMODULE v2; // rcx
  HMODULE v3; // rcx
  HMODULE v4; // rcx
  HMODULE v5; // rcx
  HMODULE v6; // rcx
  HMODULE v7; // rcx
  HMODULE v8; // rcx
  HMODULE v9; // rcx
  HMODULE v10; // rcx
  HMODULE v11; // rcx
  HMODULE v12; // rcx
  HMODULE v13; // rcx
  HMODULE v14; // rcx
  HMODULE v15; // rcx
  HMODULE v16; // rcx
  HMODULE v17; // rcx
  HMODULE v18; // rcx
  HMODULE v19; // rcx
  HMODULE v20; // rcx
  HMODULE v21; // rcx
  HMODULE v22; // rcx
  HMODULE v23; // rcx
  HMODULE v24; // rcx
  HANDLE *v25; // rsi
  HANDLE *v26; // rbx

  *(_QWORD *)this = &Win32LiveSystemProvider::`vftable'{for `MiniDumpSystemProvider'};
  *((_QWORD *)this + 1) = &Win32LiveSystemProvider::`vftable'{for `MiniDumpVmHookedProvider'};
  v2 = (HMODULE)*((_QWORD *)this + 14);
  if ( v2 )
  {
    FreeLibrary(v2);
    *((_QWORD *)this + 14) = 0;
  }
  v3 = (HMODULE)*((_QWORD *)this + 56);
  if ( v3 )
  {
    FreeLibrary(v3);
    *((_QWORD *)this + 56) = 0;
  }
  v4 = (HMODULE)*((_QWORD *)this + 59);
  if ( v4 )
  {
    FreeLibrary(v4);
    *((_QWORD *)this + 59) = 0;
  }
  v5 = (HMODULE)*((_QWORD *)this + 62);
  if ( v5 )
  {
    FreeLibrary(v5);
    *((_QWORD *)this + 62) = 0;
  }
  v6 = (HMODULE)*((_QWORD *)this + 15);
  if ( v6 )
  {
    FreeLibrary(v6);
    *((_QWORD *)this + 15) = 0;
  }
  v7 = (HMODULE)*((_QWORD *)this + 16);
  if ( v7 )
  {
    FreeLibrary(v7);
    *((_QWORD *)this + 16) = 0;
  }
  v8 = (HMODULE)*((_QWORD *)this + 17);
  if ( v8 )
  {
    FreeLibrary(v8);
    *((_QWORD *)this + 17) = 0;
  }
  v9 = (HMODULE)*((_QWORD *)this + 18);
  if ( v9 )
  {
    FreeLibrary(v9);
    *((_QWORD *)this + 18) = 0;
  }
  v10 = (HMODULE)*((_QWORD *)this + 19);
  if ( v10 )
  {
    FreeLibrary(v10);
    *((_QWORD *)this + 19) = 0;
  }
  v11 = (HMODULE)*((_QWORD *)this + 20);
  if ( v11 )
  {
    FreeLibrary(v11);
    *((_QWORD *)this + 20) = 0;
  }
  v12 = (HMODULE)*((_QWORD *)this + 21);
  if ( v12 )
  {
    FreeLibrary(v12);
    *((_QWORD *)this + 21) = 0;
  }
  v13 = (HMODULE)*((_QWORD *)this + 22);
  if ( v13 )
  {
    FreeLibrary(v13);
    *((_QWORD *)this + 22) = 0;
  }
  v14 = (HMODULE)*((_QWORD *)this + 23);
  if ( v14 )
  {
    FreeLibrary(v14);
    *((_QWORD *)this + 23) = 0;
  }
  v15 = (HMODULE)*((_QWORD *)this + 24);
  if ( v15 )
  {
    FreeLibrary(v15);
    *((_QWORD *)this + 24) = 0;
  }
  v16 = (HMODULE)*((_QWORD *)this + 25);
  if ( v16 )
  {
    FreeLibrary(v16);
    *((_QWORD *)this + 25) = 0;
  }
  v17 = (HMODULE)*((_QWORD *)this + 26);
  if ( v17 )
  {
    FreeLibrary(v17);
    *((_QWORD *)this + 26) = 0;
  }
  v18 = (HMODULE)*((_QWORD *)this + 27);
  if ( v18 )
  {
    FreeLibrary(v18);
    *((_QWORD *)this + 27) = 0;
  }
  v19 = (HMODULE)*((_QWORD *)this + 28);
  if ( v19 )
  {
    FreeLibrary(v19);
    *((_QWORD *)this + 28) = 0;
  }
  v20 = (HMODULE)*((_QWORD *)this + 29);
  if ( v20 )
  {
    FreeLibrary(v20);
    *((_QWORD *)this + 29) = 0;
  }
  v21 = (HMODULE)*((_QWORD *)this + 30);
  if ( v21 )
  {
    FreeLibrary(v21);
    *((_QWORD *)this + 30) = 0;
  }
  v22 = (HMODULE)*((_QWORD *)this + 31);
  if ( v22 )
  {
    FreeLibrary(v22);
    *((_QWORD *)this + 31) = 0;
  }
  v23 = (HMODULE)*((_QWORD *)this + 75);
  if ( v23 )
  {
    FreeLibrary(v23);
    *((_QWORD *)this + 75) = 0;
  }
  v24 = (HMODULE)*((_QWORD *)this + 79);
  if ( v24 )
  {
    FreeLibrary(v24);
    *((_QWORD *)this + 79) = 0;
  }
  v25 = (HANDLE *)*((_QWORD *)this + 96);
  while ( v25 != (HANDLE *)((char *)this + 768) )
  {
    v26 = v25;
    CloseHandle(v25[2]);
    v25 = (HANDLE *)*v25;
    (*(void (__fastcall **)(_QWORD, HANDLE *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v26);
  }
  MiniDumpOsImports::~MiniDumpOsImports((Win32LiveSystemProvider *)((char *)this + 72));
  *((_QWORD *)this + 1) = &MiniDumpVmHookedProvider::`vftable';
}

```

## disassembly

```asm
0x1800110a8  push    rbx
0x1800110aa  push    rsi
0x1800110ab  push    rdi
0x1800110ac  push    r14
0x1800110ae  sub     rsp, 38h
0x1800110b2  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800110bb  mov     rdi, rcx
0x1800110be  lea     rax, ??_7Win32LiveSystemProvider@@6BMiniDumpSystemProvider@@@; const Win32LiveSystemProvider::`vftable'{for `MiniDumpSystemProvider'}
0x1800110c5  mov     [rcx], rax
0x1800110c8  lea     rax, ??_7Win32LiveSystemProvider@@6BMiniDumpVmHookedProvider@@@; const Win32LiveSystemProvider::`vftable'{for `MiniDumpVmHookedProvider'}
0x1800110cf  mov     [rcx+8], rax
0x1800110d3  mov     rcx, [rcx+70h]; hLibModule
0x1800110d7  xor     ebx, ebx
0x1800110d9  test    rcx, rcx
0x1800110dc  jz      short loc_1800110E8
0x1800110de  call    cs:__imp_FreeLibrary
0x1800110e4  mov     [rdi+70h], rbx
0x1800110e8  mov     rcx, [rdi+1C0h]; hLibModule
0x1800110ef  test    rcx, rcx
0x1800110f2  jz      short loc_180011101
0x1800110f4  call    cs:__imp_FreeLibrary
0x1800110fa  mov     [rdi+1C0h], rbx
0x180011101  mov     rcx, [rdi+1D8h]; hLibModule
0x180011108  test    rcx, rcx
0x18001110b  jz      short loc_18001111A
0x18001110d  call    cs:__imp_FreeLibrary
0x180011113  mov     [rdi+1D8h], rbx
0x18001111a  mov     rcx, [rdi+1F0h]; hLibModule
0x180011121  test    rcx, rcx
0x180011124  jz      short loc_180011133
0x180011126  call    cs:__imp_FreeLibrary
0x18001112c  mov     [rdi+1F0h], rbx
0x180011133  mov     rcx, [rdi+78h]; hLibModule
0x180011137  test    rcx, rcx
0x18001113a  jz      short loc_180011146
0x18001113c  call    cs:__imp_FreeLibrary
0x180011142  mov     [rdi+78h], rbx
0x180011146  mov     rcx, [rdi+80h]; hLibModule
0x18001114d  test    rcx, rcx
0x180011150  jz      short loc_18001115F
0x180011152  call    cs:__imp_FreeLibrary
0x180011158  mov     [rdi+80h], rbx
0x18001115f  mov     rcx, [rdi+88h]; hLibModule
0x180011166  test    rcx, rcx
0x180011169  jz      short loc_180011178
0x18001116b  call    cs:__imp_FreeLibrary
0x180011171  mov     [rdi+88h], rbx
0x180011178  mov     rcx, [rdi+90h]; hLibModule
0x18001117f  test    rcx, rcx
0x180011182  jz      short loc_180011191
0x180011184  call    cs:__imp_FreeLibrary
0x18001118a  mov     [rdi+90h], rbx
0x180011191  mov     rcx, [rdi+98h]; hLibModule
0x180011198  test    rcx, rcx
0x18001119b  jz      short loc_1800111AA
0x18001119d  call    cs:__imp_FreeLibrary
0x1800111a3  mov     [rdi+98h], rbx
0x1800111aa  mov     rcx, [rdi+0A0h]; hLibModule
0x1800111b1  test    rcx, rcx
0x1800111b4  jz      short loc_1800111C3
0x1800111b6  call    cs:__imp_FreeLibrary
0x1800111bc  mov     [rdi+0A0h], rbx
0x1800111c3  mov     rcx, [rdi+0A8h]; hLibModule
0x1800111ca  test    rcx, rcx
0x1800111cd  jz      short loc_1800111DC
0x1800111cf  call    cs:__imp_FreeLibrary
0x1800111d5  mov     [rdi+0A8h], rbx
0x1800111dc  mov     rcx, [rdi+0B0h]; hLibModule
0x1800111e3  test    rcx, rcx
0x1800111e6  jz      short loc_1800111F5
0x1800111e8  call    cs:__imp_FreeLibrary
0x1800111ee  mov     [rdi+0B0h], rbx
0x1800111f5  mov     rcx, [rdi+0B8h]; hLibModule
0x1800111fc  test    rcx, rcx
0x1800111ff  jz      short loc_18001120E
0x180011201  call    cs:__imp_FreeLibrary
0x180011207  mov     [rdi+0B8h], rbx
0x18001120e  mov     rcx, [rdi+0C0h]; hLibModule
0x180011215  test    rcx, rcx
0x180011218  jz      short loc_180011227
0x18001121a  call    cs:__imp_FreeLibrary
0x180011220  mov     [rdi+0C0h], rbx
0x180011227  mov     rcx, [rdi+0C8h]; hLibModule
0x18001122e  test    rcx, rcx
0x180011231  jz      short loc_180011240
0x180011233  call    cs:__imp_FreeLibrary
0x180011239  mov     [rdi+0C8h], rbx
0x180011240  mov     rcx, [rdi+0D0h]; hLibModule
0x180011247  test    rcx, rcx
0x18001124a  jz      short loc_180011259
0x18001124c  call    cs:__imp_FreeLibrary
0x180011252  mov     [rdi+0D0h], rbx
0x180011259  mov     rcx, [rdi+0D8h]; hLibModule
0x180011260  test    rcx, rcx
0x180011263  jz      short loc_180011272
0x180011265  call    cs:__imp_FreeLibrary
0x18001126b  mov     [rdi+0D8h], rbx
0x180011272  mov     rcx, [rdi+0E0h]; hLibModule
0x180011279  test    rcx, rcx
0x18001127c  jz      short loc_18001128B
0x18001127e  call    cs:__imp_FreeLibrary
0x180011284  mov     [rdi+0E0h], rbx
0x18001128b  mov     rcx, [rdi+0E8h]; hLibModule
0x180011292  test    rcx, rcx
0x180011295  jz      short loc_1800112A4
0x180011297  call    cs:__imp_FreeLibrary
0x18001129d  mov     [rdi+0E8h], rbx
0x1800112a4  mov     rcx, [rdi+0F0h]; hLibModule
0x1800112ab  test    rcx, rcx
0x1800112ae  jz      short loc_1800112BD
0x1800112b0  call    cs:__imp_FreeLibrary
0x1800112b6  mov     [rdi+0F0h], rbx
0x1800112bd  mov     rcx, [rdi+0F8h]; hLibModule
0x1800112c4  test    rcx, rcx
0x1800112c7  jz      short loc_1800112D6
0x1800112c9  call    cs:__imp_FreeLibrary
0x1800112cf  mov     [rdi+0F8h], rbx
0x1800112d6  mov     rcx, [rdi+258h]; hLibModule
0x1800112dd  test    rcx, rcx
0x1800112e0  jz      short loc_1800112EF
0x1800112e2  call    cs:__imp_FreeLibrary
0x1800112e8  mov     [rdi+258h], rbx
0x1800112ef  mov     rcx, [rdi+278h]; hLibModule
0x1800112f6  test    rcx, rcx
0x1800112f9  jz      short loc_180011308
0x1800112fb  call    cs:__imp_FreeLibrary
0x180011301  mov     [rdi+278h], rbx
0x180011308  lea     r14, [rdi+300h]
0x18001130f  mov     rsi, [r14]
0x180011312  jmp     short loc_180011337
0x180011314  mov     rbx, rsi
0x180011317  mov     rcx, [rsi+10h]; hObject
0x18001131b  call    cs:__imp_CloseHandle
0x180011321  mov     rsi, [rsi]
0x180011324  mov     rcx, [rdi+30h]
0x180011328  mov     rax, [rcx]
0x18001132b  mov     rdx, rbx
0x18001132e  mov     rax, [rax+18h]
0x180011332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011337  cmp     rsi, r14
0x18001133a  jnz     short loc_180011314
0x18001133c  lea     rcx, [rdi+48h]; this
0x180011340  call    ??1MiniDumpOsImports@@QEAA@XZ; MiniDumpOsImports::~MiniDumpOsImports(void)
0x180011345  lea     rax, ??_7MiniDumpVmHookedProvider@@6B@; const MiniDumpVmHookedProvider::`vftable'
0x18001134c  mov     [rdi+8], rax
0x180011350  add     rsp, 38h
0x180011354  pop     r14
0x180011356  pop     rdi
0x180011357  pop     rsi
0x180011358  pop     rbx
0x180011359  retn
```
