# CMappedDrivesFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180033800`
- end: `0x1800338e4`
- name: `?CreateViewObject@CMappedDrivesFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `228`
- prototype: `int(CMappedDrivesFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180033800`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800338c3`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800338c3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180033834`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180033834`

## pseudocode

```c
HRESULT __fastcall CMappedDrivesFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        IShellView **a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  SFV_CREATE pcsfv; // [rsp+20h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-78h] BYREF

  StringFromGUID2(a3, sz, 39);
  v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v7 )
  {
    v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_INewItemAdvisor.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_INewItemAdvisor.Data1 )
      v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_INewItemAdvisor.Data4;
    if ( v8 )
    {
      *a4 = 0;
      return -2147467262;
    }
    else
    {
      return (**(__int64 (__fastcall ***)(char *, const struct _GUID *, IShellView **))(this - 16))(
               (char *)(this - 16),
               a3,
               a4);
    }
  }
  else
  {
    *(_QWORD *)&pcsfv.cbSize = 32;
    *(_OWORD *)&pcsfv.psvOuter = 0;
    pcsfv.pshf = (IShellFolder *)(this & -(__int64)(this != 16));
    return SHCreateShellFolderView(&pcsfv, a4);
  }
}

```

## disassembly

```asm
0x180033800  push    rbx
0x180033802  push    rsi
0x180033803  push    rdi
0x180033804  sub     rsp, 0A0h
0x18003380b  mov     rax, cs:__security_cookie
0x180033812  xor     rax, rsp
0x180033815  mov     [rsp+0B8h+var_28], rax
0x18003381d  mov     rbx, r8
0x180033820  lea     rdx, [rsp+0B8h+sz]; lpsz
0x180033825  mov     rsi, rcx
0x180033828  mov     r8d, 27h ; '''; cchMax
0x18003382e  mov     rcx, rbx; rguid
0x180033831  mov     rdi, r9
0x180033834  call    cs:__imp_StringFromGUID2
0x18003383a  mov     rax, [rbx]
0x18003383d  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180033844  jnz     short loc_180033851
0x180033846  mov     rax, [rbx+8]
0x18003384a  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180033851  test    rax, rax
0x180033854  jz      short loc_180033897
0x180033856  mov     rax, [rbx]
0x180033859  sub     rax, qword ptr cs:IID_INewItemAdvisor.Data1
0x180033860  jnz     short loc_18003386D
0x180033862  mov     rax, [rbx+8]
0x180033866  sub     rax, qword ptr cs:IID_INewItemAdvisor.Data4
0x18003386d  test    rax, rax
0x180033870  jnz     short loc_180033889
0x180033872  lea     rcx, [rsi-10h]
0x180033876  mov     r8, rdi
0x180033879  mov     rax, [rcx]
0x18003387c  mov     rdx, rbx
0x18003387f  mov     rax, [rax]
0x180033882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033887  jmp     short loc_1800338C9
0x180033889  mov     qword ptr [rdi], 0
0x180033890  mov     eax, 80004002h
0x180033895  jmp     short loc_1800338C9
0x180033897  xorps   xmm0, xmm0
0x18003389a  mov     qword ptr [rsp+0B8h+pcsfv.cbSize], 20h ; ' '
0x1800338a3  lea     rax, [rsi-10h]
0x1800338a7  mov     rdx, rdi; ppsv
0x1800338aa  neg     rax
0x1800338ad  movdqu  xmmword ptr [rsp+0B8h+pcsfv.psvOuter], xmm0
0x1800338b3  sbb     rcx, rcx
0x1800338b6  and     rcx, rsi
0x1800338b9  mov     [rsp+0B8h+pcsfv.pshf], rcx
0x1800338be  lea     rcx, [rsp+0B8h+pcsfv]; pcsfv
0x1800338c3  call    cs:__imp_SHCreateShellFolderView
0x1800338c9  mov     rcx, [rsp+0B8h+var_28]
0x1800338d1  xor     rcx, rsp; StackCookie
0x1800338d4  call    __security_check_cookie
0x1800338d9  add     rsp, 0A0h
0x1800338e0  pop     rdi
0x1800338e1  pop     rsi
0x1800338e2  pop     rbx
0x1800338e3  retn
```
