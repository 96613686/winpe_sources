# VsUI::GdiplusImage::CreateStreamOnResource(HINSTANCE__ *,HRSRC__ *,IStream * *)

- ea: `0x14002e3e0`
- end: `0x14002e507`
- name: `?CreateStreamOnResource@GdiplusImage@VsUI@@CAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z`
- size: `295`
- prototype: `__int64 __fastcall(HINSTANCE hModule, HRSRC hResInfo, struct IStream **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f240`

## callees

- `0x140001020`
- `0x14002e3e0`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x14002e463`
- `KERNEL32!SizeofResource` at `0x14002e463`
- `KERNEL32!LockResource` at `0x14002e46e`
- `KERNEL32!LockResource` at `0x14002e46e`
- `KERNEL32!LoadResource` at `0x14002e420`
- `KERNEL32!LoadResource` at `0x14002e420`
- `ole32!CreateStreamOnHGlobal` at `0x14002e444`
- `ole32!CreateStreamOnHGlobal` at `0x14002e444`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VsUI::GdiplusImage::CreateStreamOnResource(HINSTANCE hModule, HRSRC hResInfo, struct IStream **a3)
{
  HGLOBAL Resource; // rbp
  HRESULT v8; // ebx
  LPSTREAM v9; // rbx
  struct IStreamVtbl *lpVtbl; // rsi
  DWORD v11; // edi
  LPVOID v12; // rax
  LPSTREAM v13; // rcx
  LPSTREAM ppstm; // [rsp+28h] [rbp-40h] BYREF
  int v15; // [rsp+30h] [rbp-38h] BYREF

  if ( !a3 )
    return 2147500035LL;
  if ( !hResInfo )
    return 2147942487LL;
  Resource = LoadResource(hModule, hResInfo);
  if ( !Resource )
    return 2147942487LL;
  ppstm = 0;
  v8 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v8 < 0
    || (v15 = 0,
        v9 = ppstm,
        lpVtbl = ppstm->lpVtbl,
        v11 = SizeofResource(hModule, hResInfo),
        v12 = LockResource(Resource),
        v8 = ((__int64 (__fastcall *)(LPSTREAM, LPVOID, _QWORD, int *))lpVtbl->Write)(v9, v12, v11, &v15),
        v8 < 0)
    || (v8 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0, 0),
        v8 < 0) )
  {
    v13 = ppstm;
  }
  else
  {
    v13 = ppstm;
    *a3 = ppstm;
    if ( v13 )
    {
      ((void (__fastcall *)(LPSTREAM))v13->lpVtbl->AddRef)(v13);
      v13 = ppstm;
    }
    v8 = 0;
  }
  if ( v13 )
    ((void (__fastcall *)(LPSTREAM))v13->lpVtbl->Release)(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14002e3e0  mov     [rsp+arg_18], rbx
0x14002e3e5  push    rbp
0x14002e3e6  push    rsi
0x14002e3e7  push    rdi
0x14002e3e8  push    r14
0x14002e3ea  push    r15
0x14002e3ec  sub     rsp, 40h
0x14002e3f0  mov     rax, cs:__security_cookie
0x14002e3f7  xor     rax, rsp
0x14002e3fa  mov     [rsp+68h+var_30], rax
0x14002e3ff  mov     r14, r8
0x14002e402  mov     rdi, rdx
0x14002e405  mov     r15, rcx
0x14002e408  test    r8, r8
0x14002e40b  jnz     short loc_14002E417
0x14002e40d  mov     eax, 80004003h
0x14002e412  jmp     loc_14002E4E6
0x14002e417  test    rdi, rdi
0x14002e41a  jz      loc_14002E4E1
0x14002e420  call    cs:__imp_LoadResource
0x14002e426  mov     rbp, rax
0x14002e429  test    rax, rax
0x14002e42c  jz      loc_14002E4E1
0x14002e432  and     [rsp+68h+ppstm], 0
0x14002e438  lea     r8, [rsp+68h+ppstm]; ppstm
0x14002e43d  mov     edx, 1; fDeleteOnRelease
0x14002e442  xor     ecx, ecx; hGlobal
0x14002e444  call    cs:__imp_CreateStreamOnHGlobal
0x14002e44a  mov     ebx, eax
0x14002e44c  test    eax, eax
0x14002e44e  js      short loc_14002E4CD
0x14002e450  and     [rsp+68h+var_38], 0
0x14002e455  mov     rbx, [rsp+68h+ppstm]
0x14002e45a  mov     rsi, [rbx]
0x14002e45d  mov     rdx, rdi; hResInfo
0x14002e460  mov     rcx, r15; hModule
0x14002e463  call    cs:__imp_SizeofResource
0x14002e469  mov     edi, eax
0x14002e46b  mov     rcx, rbp; hResData
0x14002e46e  call    cs:__imp_LockResource
0x14002e474  mov     rdx, rax
0x14002e477  lea     r9, [rsp+68h+var_38]
0x14002e47c  mov     r8d, edi
0x14002e47f  mov     rcx, rbx
0x14002e482  call    qword ptr [rsi+20h]
0x14002e485  mov     ebx, eax
0x14002e487  test    eax, eax
0x14002e489  js      short loc_14002E4CD
0x14002e48b  and     dword ptr [rsp+68h+var_48], 0
0x14002e490  and     dword ptr [rsp+68h+var_48+4], 0
0x14002e495  mov     rcx, [rsp+68h+ppstm]
0x14002e49a  mov     rax, [rcx]
0x14002e49d  xor     r9d, r9d
0x14002e4a0  xor     r8d, r8d
0x14002e4a3  mov     rdx, [rsp+68h+var_48]
0x14002e4a8  call    qword ptr [rax+28h]
0x14002e4ab  mov     ebx, eax
0x14002e4ad  test    eax, eax
0x14002e4af  js      short loc_14002E4CD
0x14002e4b1  mov     rcx, [rsp+68h+ppstm]
0x14002e4b6  mov     [r14], rcx
0x14002e4b9  test    rcx, rcx
0x14002e4bc  jz      short loc_14002E4C9
0x14002e4be  mov     rax, [rcx]
0x14002e4c1  call    qword ptr [rax+8]
0x14002e4c4  mov     rcx, [rsp+68h+ppstm]
0x14002e4c9  xor     ebx, ebx
0x14002e4cb  jmp     short loc_14002E4D2
0x14002e4cd  mov     rcx, [rsp+68h+ppstm]
0x14002e4d2  test    rcx, rcx
0x14002e4d5  jz      short loc_14002E4DD
0x14002e4d7  mov     rdx, [rcx]
0x14002e4da  call    qword ptr [rdx+10h]
0x14002e4dd  mov     eax, ebx
0x14002e4df  jmp     short loc_14002E4E6
0x14002e4e1  mov     eax, 80070057h
0x14002e4e6  mov     rcx, [rsp+68h+var_30]
0x14002e4eb  xor     rcx, rsp; StackCookie
0x14002e4ee  call    __security_check_cookie
0x14002e4f3  mov     rbx, [rsp+68h+arg_18]
0x14002e4fb  add     rsp, 40h
0x14002e4ff  pop     r15
0x14002e501  pop     r14
0x14002e503  pop     rdi
0x14002e504  pop     rsi
0x14002e505  pop     rbp
0x14002e506  retn
```
