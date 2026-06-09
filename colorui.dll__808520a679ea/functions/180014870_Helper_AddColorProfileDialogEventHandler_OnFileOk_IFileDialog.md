# Helper::AddColorProfileDialogEventHandler::OnFileOk(IFileDialog *)

- ea: `0x180014870`
- end: `0x180014a21`
- name: `?OnFileOk@AddColorProfileDialogEventHandler@Helper@@UEAAJPEAUIFileDialog@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(HINSTANCE *this, struct IFileDialog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x180014870`
- `0x180015c5c`
- `0x18001772c`
- `0x180017ab0`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `mscms!CloseColorProfile` at `0x1800149d2`
- `mscms!GetColorProfileHeader` at `0x1800149ad`
- `mscms!GetColorProfileHeader` at `0x1800149ad`
- `mscms!OpenColorProfileW` at `0x18001495e`
- `mscms!OpenColorProfileW` at `0x18001495e`

## pseudocode

```c
__int64 __fastcall Helper::AddColorProfileDialogEventHandler::OnFileOk(HINSTANCE *this, struct IFileDialog *a2)
{
  struct IFileDialogVtbl *lpVtbl; // rax
  int v4; // edi
  int v5; // eax
  __int16 *v6; // rcx
  __int64 v7; // rax
  HPROFILE v8; // rbx
  unsigned __int16 *v10; // [rsp+20h] [rbp-89h] BYREF
  __int64 v11; // [rsp+28h] [rbp-81h] BYREF
  int v12; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 *v13; // [rsp+38h] [rbp-71h]
  PROFILE pProfile; // [rsp+40h] [rbp-69h] BYREF
  PROFILEHEADER pHeader; // [rsp+60h] [rbp-49h] BYREF

  lpVtbl = a2->lpVtbl;
  v11 = 0;
  v4 = ((__int64 (__fastcall *)(struct IFileDialog *, __int64 *))lpVtbl->GetResult)(a2, &v11);
  if ( v4 >= 0 )
  {
    v10 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)v11 + 40LL))(
           v11,
           2147844096LL,
           &v10);
    if ( v4 < 0 )
    {
LABEL_16:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      return (unsigned int)v4;
    }
    v13 = &NCoreLibrary::TString::gszNullState;
    v12 = 1735554163;
    v5 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)&v12, v10);
    *(_QWORD *)&pProfile.dwType = 1;
    v6 = &word_180021DD6;
    if ( v5 >= 0 )
      v6 = (__int16 *)v13;
    v4 = 1;
    pProfile.pProfileData = v10;
    v7 = -1;
    v13 = (unsigned __int16 *)v6;
    *(_QWORD *)&pProfile.cbDataSize = 0;
    do
      ++v7;
    while ( v6[v7] );
    pProfile.cbDataSize = 2 * v7;
    v8 = OpenColorProfileW(&pProfile, 1u, 1u, 3u);
    if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      memset_0(&pHeader, 0, sizeof(pHeader));
      if ( GetColorProfileHeader(v8, &pHeader) )
        v4 = 0;
      else
        Helper::ShowErrorDialog(this[4], this[3], (HWND)0x139A, 0, (int)v10);
    }
    else
    {
      Helper::ShowErrorDialog(this[4], this[3], (HWND)0x139A, 0, (int)v10);
      if ( !v8 || v8 == (HPROFILE)-1LL )
        goto LABEL_15;
    }
    ((void (__fastcall *)(HPROFILE))CloseColorProfile)(v8);
LABEL_15:
    NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v12);
    goto LABEL_16;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180014870  mov     [rsp-8+arg_10], rbx
0x180014875  mov     [rsp-8+arg_18], rsi
0x18001487a  push    rbp
0x18001487b  push    rdi
0x18001487c  push    r14
0x18001487e  lea     rbp, [rsp-47h]
0x180014883  sub     rsp, 0F0h
0x18001488a  mov     rax, cs:__security_cookie
0x180014891  xor     rax, rsp
0x180014894  mov     [rbp+57h+var_20], rax
0x180014898  mov     rax, [rdx]
0x18001489b  mov     r8, rdx
0x18001489e  mov     rsi, rcx
0x1800148a1  lea     rdx, [rsp+100h+var_D8]
0x1800148a6  xor     r14d, r14d
0x1800148a9  mov     rcx, r8
0x1800148ac  mov     [rsp+100h+var_D8], r14
0x1800148b1  mov     rax, [rax+0A0h]
0x1800148b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148bd  mov     edi, eax
0x1800148bf  test    eax, eax
0x1800148c1  js      loc_1800149FB
0x1800148c7  mov     rcx, [rsp+100h+var_D8]
0x1800148cc  lea     r8, [rsp+100h+var_E0]
0x1800148d1  mov     [rsp+100h+var_E0], r14; int
0x1800148d6  mov     edx, 80058000h
0x1800148db  mov     rax, [rcx]
0x1800148de  mov     rax, [rax+28h]
0x1800148e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148e7  mov     edi, eax
0x1800148e9  test    eax, eax
0x1800148eb  js      loc_1800149EA
0x1800148f1  mov     rdx, [rsp+100h+var_E0]; unsigned __int16 *
0x1800148f6  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x1800148fd  lea     rcx, [rbp+57h+var_D0]; this
0x180014901  mov     [rbp+57h+var_C8], rax
0x180014905  mov     [rbp+57h+var_D0], 67727473h
0x18001490c  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x180014911  test    eax, eax
0x180014913  mov     qword ptr [rbp+57h+pProfile.dwType], 1
0x18001491b  mov     rax, [rsp+100h+var_E0]
0x180014920  lea     rcx, word_180021DD6
0x180014927  cmovns  rcx, [rbp+57h+var_C8]
0x18001492c  lea     edi, [r14+1]
0x180014930  mov     [rbp+57h+pProfile.pProfileData], rax
0x180014934  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014938  mov     [rbp+57h+var_C8], rcx
0x18001493c  mov     qword ptr [rbp+57h+pProfile.cbDataSize], r14
0x180014940  inc     rax
0x180014943  cmp     [rcx+rax*2], r14w
0x180014948  jnz     short loc_180014940
0x18001494a  add     eax, eax
0x18001494c  lea     rcx, [rbp+57h+pProfile]; pProfile
0x180014950  mov     r9d, 3; dwCreationMode
0x180014956  mov     [rbp+57h+pProfile.cbDataSize], eax
0x180014959  mov     r8d, edi; dwShareMode
0x18001495c  mov     edx, edi; dwDesiredAccess
0x18001495e  call    cs:__imp_OpenColorProfileW
0x180014964  mov     rbx, rax
0x180014967  inc     rax
0x18001496a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180014970  jnz     short loc_180014995
0x180014972  mov     rdx, [rsi+18h]; HINSTANCE
0x180014976  xor     r9d, r9d; unsigned int
0x180014979  mov     rcx, [rsi+20h]; this
0x18001497d  mov     r8d, 139Ah; HWND
0x180014983  call    ?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@IJ@Z; Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,uint,long)
0x180014988  test    rbx, rbx
0x18001498b  jz      short loc_1800149E1
0x18001498d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180014991  jnz     short loc_1800149D2
0x180014993  jmp     short loc_1800149E1
0x180014995  xor     edx, edx; Val
0x180014997  lea     rcx, [rbp+57h+pHeader]; void *
0x18001499b  mov     r8d, 80h; Size
0x1800149a1  call    memset_0
0x1800149a6  lea     rdx, [rbp+57h+pHeader]; pHeader
0x1800149aa  mov     rcx, rbx; hProfile
0x1800149ad  call    cs:__imp_GetColorProfileHeader
0x1800149b3  test    eax, eax
0x1800149b5  jz      short loc_1800149BC
0x1800149b7  mov     edi, r14d
0x1800149ba  jmp     short loc_1800149D2
0x1800149bc  mov     rdx, [rsi+18h]; HINSTANCE
0x1800149c0  xor     r9d, r9d; unsigned int
0x1800149c3  mov     rcx, [rsi+20h]; this
0x1800149c7  mov     r8d, 139Ah; HWND
0x1800149cd  call    ?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@IJ@Z; Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,uint,long)
0x1800149d2  mov     rax, cs:__imp_CloseColorProfile
0x1800149d9  mov     rcx, rbx
0x1800149dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e1  lea     rcx, [rbp+57h+var_D0]; this
0x1800149e5  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x1800149ea  mov     rcx, [rsp+100h+var_D8]
0x1800149ef  mov     rax, [rcx]
0x1800149f2  mov     rax, [rax+10h]
0x1800149f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149fb  mov     eax, edi
0x1800149fd  mov     rcx, [rbp+57h+var_20]
0x180014a01  xor     rcx, rsp; StackCookie
0x180014a04  call    __security_check_cookie
0x180014a09  lea     r11, [rsp+100h+var_10]
0x180014a11  mov     rbx, [r11+30h]
0x180014a15  mov     rsi, [r11+38h]
0x180014a19  mov     rsp, r11
0x180014a1c  pop     r14
0x180014a1e  pop     rdi
0x180014a1f  pop     rbp
0x180014a20  retn
```
