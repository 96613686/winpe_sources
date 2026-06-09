# DeviceClose(_MCIGRAPHIC *)

- ea: `0x180001f60`
- end: `0x18000224d`
- name: `?DeviceClose@@YAKPEAU_MCIGRAPHIC@@@Z`
- size: `749`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004de0`

## callees

- `0x180001f60`
- `0x1800041fc`
- `0x180004f9c`
- `0x180007010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180002042`
- `KERNEL32!WaitForSingleObject` at `0x180002042`
- `KERNEL32!CloseHandle` at `0x18000204f`
- `KERNEL32!CloseHandle` at `0x180002228`
- `KERNEL32!CloseHandle` at `0x18000223a`
- `KERNEL32!CloseHandle` at `0x18000204f`
- `KERNEL32!CloseHandle` at `0x180002228`
- `KERNEL32!CloseHandle` at `0x18000223a`
- `KERNEL32!SetEvent` at `0x180002032`
- `KERNEL32!SetEvent` at `0x180002032`
- `USER32!DestroyWindow` at `0x180001ffe`
- `USER32!DestroyWindow` at `0x180001ffe`
- `USER32!UnregisterClassW` at `0x180002012`
- `USER32!UnregisterClassW` at `0x180002012`
- `GDI32!DeleteObject` at `0x18000220e`
- `GDI32!DeleteObject` at `0x18000220e`

## pseudocode

```c
__int64 __fastcall DeviceClose(struct _MCIGRAPHIC *a1)
{
  __int64 v2; // rcx
  HWND v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx

  if ( *((_QWORD *)a1 + 19) )
  {
    GraphicDelayedNotify(a1, 4);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 72LL))(*((_QWORD *)a1 + 19));
  }
  v2 = *((_QWORD *)a1 + 22);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 152LL))(v2, 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 22) + 248LL))(*((_QWORD *)a1 + 22), 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 22) + 72LL))(*((_QWORD *)a1 + 22), 0);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 22) + 232LL))(*((_QWORD *)a1 + 22), 0);
    v3 = (HWND)*((_QWORD *)a1 + 6);
    if ( v3 )
    {
      DestroyWindow(v3);
      UnregisterClassW(L"MCIQTZ_Window", ghModule);
    }
  }
  if ( *((_QWORD *)a1 + 32) )
  {
    v4 = (void *)*((_QWORD *)a1 + 35);
    *((_DWORD *)a1 + 63) = 1;
    SetEvent(v4);
    WaitForSingleObject(*((HANDLE *)a1 + 32), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)a1 + 32));
    *((_QWORD *)a1 + 32) = 0;
  }
  v5 = *((_QWORD *)a1 + 14);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)a1 + 14) = 0;
  }
  v6 = *((_QWORD *)a1 + 15);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)a1 + 15) = 0;
  }
  v7 = *((_QWORD *)a1 + 16);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)a1 + 16) = 0;
  }
  v8 = *((_QWORD *)a1 + 17);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *((_QWORD *)a1 + 17) = 0;
  }
  v9 = *((_QWORD *)a1 + 19);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)a1 + 19) = 0;
  }
  v10 = *((_QWORD *)a1 + 20);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)a1 + 20) = 0;
  }
  v11 = *((_QWORD *)a1 + 18);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    *((_QWORD *)a1 + 18) = 0;
  }
  v12 = *((_QWORD *)a1 + 41);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)a1 + 41) = 0;
  }
  v13 = *((_QWORD *)a1 + 22);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)a1 + 22) = 0;
  }
  v14 = *((_QWORD *)a1 + 21);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)a1 + 21) = 0;
  }
  v15 = *((_QWORD *)a1 + 23);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)a1 + 23) = 0;
  }
  v16 = *((_QWORD *)a1 + 42);
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    *((_QWORD *)a1 + 42) = 0;
  }
  v17 = *((_QWORD *)a1 + 67);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)a1 + 67) = 0;
  }
  v18 = *((_QWORD *)a1 + 24);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)a1 + 24) = 0;
  }
  v19 = (void *)*((_QWORD *)a1 + 40);
  if ( v19 )
    DeleteObject(v19);
  ReleaseCachedFrame(a1);
  v20 = (void *)*((_QWORD *)a1 + 33);
  if ( v20 )
    CloseHandle(v20);
  v21 = (void *)*((_QWORD *)a1 + 35);
  if ( v21 )
    CloseHandle(v21);
  return 0;
}

```

## disassembly

```asm
0x180001f60  mov     [rsp+arg_0], rbx
0x180001f65  push    rdi
0x180001f66  sub     rsp, 20h
0x180001f6a  xor     edi, edi
0x180001f6c  mov     rbx, rcx
0x180001f6f  cmp     [rcx+98h], rdi
0x180001f76  jz      short loc_180001F93
0x180001f78  lea     edx, [rdi+4]
0x180001f7b  call    GraphicDelayedNotify
0x180001f80  mov     rcx, [rbx+98h]
0x180001f87  mov     rax, [rcx]
0x180001f8a  mov     rax, [rax+48h]
0x180001f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f93  mov     rcx, [rbx+0B0h]
0x180001f9a  test    rcx, rcx
0x180001f9d  jz      short loc_180002018
0x180001f9f  mov     rax, [rcx]
0x180001fa2  xor     edx, edx
0x180001fa4  mov     rax, [rax+98h]
0x180001fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fb0  mov     rcx, [rbx+0B0h]
0x180001fb7  xor     edx, edx
0x180001fb9  mov     rax, [rcx]
0x180001fbc  mov     rax, [rax+0F8h]
0x180001fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc8  mov     rcx, [rbx+0B0h]
0x180001fcf  xor     edx, edx
0x180001fd1  mov     rax, [rcx]
0x180001fd4  mov     rax, [rax+48h]
0x180001fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fdd  mov     rcx, [rbx+0B0h]
0x180001fe4  xor     edx, edx
0x180001fe6  mov     rax, [rcx]
0x180001fe9  mov     rax, [rax+0E8h]
0x180001ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ff5  mov     rcx, [rbx+30h]; hWnd
0x180001ff9  test    rcx, rcx
0x180001ffc  jz      short loc_180002018
0x180001ffe  call    cs:__imp_DestroyWindow
0x180002004  mov     rdx, cs:?ghModule@@3PEAUHINSTANCE__@@EA; hInstance
0x18000200b  lea     rcx, ClassName; "MCIQTZ_Window"
0x180002012  call    cs:__imp_UnregisterClassW
0x180002018  cmp     [rbx+100h], rdi
0x18000201f  jz      short loc_18000205C
0x180002021  mov     rcx, [rbx+118h]; hEvent
0x180002028  mov     dword ptr [rbx+0FCh], 1
0x180002032  call    cs:__imp_SetEvent
0x180002038  mov     rcx, [rbx+100h]; hHandle
0x18000203f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002042  call    cs:__imp_WaitForSingleObject
0x180002048  mov     rcx, [rbx+100h]; hObject
0x18000204f  call    cs:__imp_CloseHandle
0x180002055  mov     [rbx+100h], rdi
0x18000205c  mov     rcx, [rbx+70h]
0x180002060  test    rcx, rcx
0x180002063  jz      short loc_180002075
0x180002065  mov     rax, [rcx]
0x180002068  mov     rax, [rax+10h]
0x18000206c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002071  mov     [rbx+70h], rdi
0x180002075  mov     rcx, [rbx+78h]
0x180002079  test    rcx, rcx
0x18000207c  jz      short loc_18000208E
0x18000207e  mov     rax, [rcx]
0x180002081  mov     rax, [rax+10h]
0x180002085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000208a  mov     [rbx+78h], rdi
0x18000208e  mov     rcx, [rbx+80h]
0x180002095  test    rcx, rcx
0x180002098  jz      short loc_1800020AD
0x18000209a  mov     rax, [rcx]
0x18000209d  mov     rax, [rax+10h]
0x1800020a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020a6  mov     [rbx+80h], rdi
0x1800020ad  mov     rcx, [rbx+88h]
0x1800020b4  test    rcx, rcx
0x1800020b7  jz      short loc_1800020CC
0x1800020b9  mov     rax, [rcx]
0x1800020bc  mov     rax, [rax+10h]
0x1800020c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c5  mov     [rbx+88h], rdi
0x1800020cc  mov     rcx, [rbx+98h]
0x1800020d3  test    rcx, rcx
0x1800020d6  jz      short loc_1800020EB
0x1800020d8  mov     rax, [rcx]
0x1800020db  mov     rax, [rax+10h]
0x1800020df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e4  mov     [rbx+98h], rdi
0x1800020eb  mov     rcx, [rbx+0A0h]
0x1800020f2  test    rcx, rcx
0x1800020f5  jz      short loc_18000210A
0x1800020f7  mov     rax, [rcx]
0x1800020fa  mov     rax, [rax+10h]
0x1800020fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002103  mov     [rbx+0A0h], rdi
0x18000210a  mov     rcx, [rbx+90h]
0x180002111  test    rcx, rcx
0x180002114  jz      short loc_180002129
0x180002116  mov     rax, [rcx]
0x180002119  mov     rax, [rax+10h]
0x18000211d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002122  mov     [rbx+90h], rdi
0x180002129  mov     rcx, [rbx+148h]
0x180002130  test    rcx, rcx
0x180002133  jz      short loc_180002148
0x180002135  mov     rax, [rcx]
0x180002138  mov     rax, [rax+10h]
0x18000213c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002141  mov     [rbx+148h], rdi
0x180002148  mov     rcx, [rbx+0B0h]
0x18000214f  test    rcx, rcx
0x180002152  jz      short loc_180002167
0x180002154  mov     rax, [rcx]
0x180002157  mov     rax, [rax+10h]
0x18000215b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002160  mov     [rbx+0B0h], rdi
0x180002167  mov     rcx, [rbx+0A8h]
0x18000216e  test    rcx, rcx
0x180002171  jz      short loc_180002186
0x180002173  mov     rax, [rcx]
0x180002176  mov     rax, [rax+10h]
0x18000217a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000217f  mov     [rbx+0A8h], rdi
0x180002186  mov     rcx, [rbx+0B8h]
0x18000218d  test    rcx, rcx
0x180002190  jz      short loc_1800021A5
0x180002192  mov     rax, [rcx]
0x180002195  mov     rax, [rax+10h]
0x180002199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219e  mov     [rbx+0B8h], rdi
0x1800021a5  mov     rcx, [rbx+150h]
0x1800021ac  test    rcx, rcx
0x1800021af  jz      short loc_1800021C4
0x1800021b1  mov     rax, [rcx]
0x1800021b4  mov     rax, [rax+10h]
0x1800021b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021bd  mov     [rbx+150h], rdi
0x1800021c4  mov     rcx, [rbx+218h]
0x1800021cb  test    rcx, rcx
0x1800021ce  jz      short loc_1800021E3
0x1800021d0  mov     rax, [rcx]
0x1800021d3  mov     rax, [rax+10h]
0x1800021d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021dc  mov     [rbx+218h], rdi
0x1800021e3  mov     rcx, [rbx+0C0h]
0x1800021ea  test    rcx, rcx
0x1800021ed  jz      short loc_180002202
0x1800021ef  mov     rax, [rcx]
0x1800021f2  mov     rax, [rax+10h]
0x1800021f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021fb  mov     [rbx+0C0h], rdi
0x180002202  mov     rcx, [rbx+140h]; ho
0x180002209  test    rcx, rcx
0x18000220c  jz      short loc_180002214
0x18000220e  call    cs:__imp_DeleteObject
0x180002214  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180002217  call    ?ReleaseCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z; ReleaseCachedFrame(_MCIGRAPHIC *)
0x18000221c  mov     rcx, [rbx+108h]; hObject
0x180002223  test    rcx, rcx
0x180002226  jz      short loc_18000222E
0x180002228  call    cs:__imp_CloseHandle
0x18000222e  mov     rcx, [rbx+118h]; hObject
0x180002235  test    rcx, rcx
0x180002238  jz      short loc_180002240
0x18000223a  call    cs:__imp_CloseHandle
0x180002240  mov     rbx, [rsp+28h+arg_0]
0x180002245  xor     eax, eax
0x180002247  add     rsp, 20h
0x18000224b  pop     rdi
0x18000224c  retn
```
