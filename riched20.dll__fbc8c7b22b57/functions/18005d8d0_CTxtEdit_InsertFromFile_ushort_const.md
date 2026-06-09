# CTxtEdit::InsertFromFile(ushort const *)

- ea: `0x18005d8d0`
- end: `0x18005dabe`
- name: `?InsertFromFile@CTxtEdit@@AEAA_JPEBG@Z`
- size: `494`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005decc`

## callees

- `0x1800427ac`
- `0x1800559d8`
- `0x18005d8d0`
- `0x1800931b0`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## string_xrefs

- `0x18005d980`: `OleCreateLinkToFile`

## pseudocode

```c
__int64 __fastcall CTxtEdit::InsertFromFile(CTxtEdit *this, const unsigned __int16 *a2)
{
  struct IRichEditOleCallback *RECallback; // rax
  struct IRichEditOleCallback *v5; // rdi
  int v7; // ebx
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v9)(const unsigned __int16 *, GUID *, __int64); // rbx
  _DWORD v10[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v11[16]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v12; // [rsp+58h] [rbp-11h]
  __int64 v13; // [rsp+60h] [rbp-9h] BYREF
  __int64 v14; // [rsp+68h] [rbp-1h] BYREF
  int v15; // [rsp+78h] [rbp+Fh]

  memset_0(v10, 0, 0x48u);
  RECallback = CTxtEdit::GetRECallback(this);
  v5 = RECallback;
  if ( !RECallback )
    return -2147467262;
  v10[0] = 72;
  v7 = ((__int64 (__fastcall *)(struct IRichEditOleCallback *, __int64 *))RECallback->lpVtbl->GetNewStorage)(
         RECallback,
         &v13);
  if ( !v7 )
  {
    v7 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8, &v14);
    if ( v14 )
    {
      Ole32Procs = CThreadData::GetOle32Procs();
      v9 = (__int64 (__fastcall **)(const unsigned __int16 *, GUID *, __int64))((char *)Ole32Procs + 88);
      if ( !*((_QWORD *)Ole32Procs + 11) )
        SetProcAddr((FARPROC *)Ole32Procs + 11, 1, "OleCreateLinkToFile");
      if ( *v9 )
      {
        v7 = (*v9)(a2, &IID_IOleObject, 1);
        if ( !v7 )
        {
          v15 = 1;
          v10[1] = -1;
          v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 120LL))(v12, v11);
          if ( !v7 )
          {
            v7 = ((__int64 (__fastcall *)(struct IRichEditOleCallback *, _BYTE *, __int64, __int64))v5->lpVtbl->QueryInsertObject)(
                   v5,
                   v11,
                   v13,
                   0xFFFFFFFFLL);
            if ( !v7 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, v14);
              if ( !v7 )
                v7 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*((_QWORD *)this + 1) + 56LL))((char *)this + 8, v10);
            }
          }
        }
      }
      else
      {
        v7 = -2147467259;
      }
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v7;
}

```

## disassembly

```asm
0x18005d8d0  mov     [rsp-8+arg_10], rbx
0x18005d8d5  push    rbp
0x18005d8d6  push    rsi
0x18005d8d7  push    rdi
0x18005d8d8  push    r14
0x18005d8da  push    r15
0x18005d8dc  lea     rbp, [rsp-37h]
0x18005d8e1  sub     rsp, 0A0h
0x18005d8e8  mov     rax, cs:__security_cookie
0x18005d8ef  xor     rax, rsp
0x18005d8f2  mov     [rbp+57h+var_30], rax
0x18005d8f6  mov     r15, rdx
0x18005d8f9  mov     rsi, rcx
0x18005d8fc  mov     ebx, 48h ; 'H'
0x18005d901  lea     rcx, [rbp+57h+var_80]; void *
0x18005d905  mov     r8d, ebx; Size
0x18005d908  xor     edx, edx; Val
0x18005d90a  call    memset_0
0x18005d90f  mov     rcx, rsi; this
0x18005d912  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x18005d917  mov     rdi, rax
0x18005d91a  test    rax, rax
0x18005d91d  jnz     short loc_18005D92B
0x18005d91f  mov     rax, 0FFFFFFFF80004002h
0x18005d926  jmp     loc_18005DA9A
0x18005d92b  mov     [rbp+57h+var_80], ebx
0x18005d92e  lea     rdx, [rbp+57h+var_60]
0x18005d932  mov     rax, [rax]
0x18005d935  mov     rcx, rdi
0x18005d938  mov     rax, [rax+18h]
0x18005d93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d941  mov     ebx, eax
0x18005d943  test    eax, eax
0x18005d945  jnz     loc_18005DA58
0x18005d94b  mov     rax, [rsi+8]
0x18005d94f  lea     rdx, [rbp+57h+var_58]
0x18005d953  lea     rcx, [rsi+8]
0x18005d957  mov     rax, [rax+18h]
0x18005d95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d960  cmp     [rbp+57h+var_58], 0
0x18005d965  mov     ebx, eax
0x18005d967  jz      loc_18005DA58
0x18005d96d  mov     r14, [rbp+57h+var_60]
0x18005d971  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18005d976  lea     rbx, [rax+58h]
0x18005d97a  cmp     qword ptr [rbx], 0
0x18005d97e  jnz     short loc_18005D994
0x18005d980  lea     r8, aOlecreatelinkt; "OleCreateLinkToFile"
0x18005d987  mov     edx, 1
0x18005d98c  mov     rcx, rbx
0x18005d98f  call    SetProcAddr
0x18005d994  mov     rax, [rbx]
0x18005d997  test    rax, rax
0x18005d99a  jz      loc_18005DA53
0x18005d9a0  xor     r9d, r9d
0x18005d9a3  lea     rcx, [rbp+57h+var_68]
0x18005d9a7  mov     [rsp+0C0h+var_90], rcx
0x18005d9ac  lea     rdx, IID_IOleObject
0x18005d9b3  mov     [rsp+0C0h+var_98], r14
0x18005d9b8  mov     rcx, r15
0x18005d9bb  mov     [rsp+0C0h+var_A0], 0
0x18005d9c4  lea     r8d, [r9+1]
0x18005d9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9cd  mov     ebx, eax
0x18005d9cf  test    eax, eax
0x18005d9d1  jnz     loc_18005DA58
0x18005d9d7  mov     rcx, [rbp+57h+var_68]
0x18005d9db  lea     rdx, [rbp+57h+var_78]
0x18005d9df  mov     [rbp+57h+var_48], 1
0x18005d9e6  or      r14d, 0FFFFFFFFh
0x18005d9ea  mov     [rbp+57h+var_7C], r14d
0x18005d9ee  mov     rax, [rcx]
0x18005d9f1  mov     rax, [rax+78h]
0x18005d9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d9fa  mov     ebx, eax
0x18005d9fc  test    eax, eax
0x18005d9fe  jnz     short loc_18005DA58
0x18005da00  mov     rax, [rdi]
0x18005da03  lea     rdx, [rbp+57h+var_78]
0x18005da07  mov     r8, [rbp+57h+var_60]
0x18005da0b  mov     r9d, r14d
0x18005da0e  mov     rcx, rdi
0x18005da11  mov     rax, [rax+30h]
0x18005da15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da1a  mov     ebx, eax
0x18005da1c  test    eax, eax
0x18005da1e  jnz     short loc_18005DA58
0x18005da20  mov     rcx, [rbp+57h+var_68]
0x18005da24  mov     rdx, [rbp+57h+var_58]
0x18005da28  mov     rax, [rcx]
0x18005da2b  mov     rax, [rax+18h]
0x18005da2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da34  mov     ebx, eax
0x18005da36  test    eax, eax
0x18005da38  jnz     short loc_18005DA58
0x18005da3a  mov     rax, [rsi+8]
0x18005da3e  lea     rdx, [rbp+57h+var_80]
0x18005da42  lea     rcx, [rsi+8]
0x18005da46  mov     rax, [rax+38h]
0x18005da4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da4f  mov     ebx, eax
0x18005da51  jmp     short loc_18005DA58
0x18005da53  mov     ebx, 80004005h
0x18005da58  mov     rcx, [rbp+57h+var_68]
0x18005da5c  test    rcx, rcx
0x18005da5f  jz      short loc_18005DA6D
0x18005da61  mov     rax, [rcx]
0x18005da64  mov     rax, [rax+10h]
0x18005da68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da6d  mov     rcx, [rbp+57h+var_58]
0x18005da71  test    rcx, rcx
0x18005da74  jz      short loc_18005DA82
0x18005da76  mov     rax, [rcx]
0x18005da79  mov     rax, [rax+10h]
0x18005da7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da82  mov     rcx, [rbp+57h+var_60]
0x18005da86  test    rcx, rcx
0x18005da89  jz      short loc_18005DA97
0x18005da8b  mov     rax, [rcx]
0x18005da8e  mov     rax, [rax+10h]
0x18005da92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005da97  movsxd  rax, ebx
0x18005da9a  mov     rcx, [rbp+57h+var_30]
0x18005da9e  xor     rcx, rsp; StackCookie
0x18005daa1  call    __security_check_cookie
0x18005daa6  mov     rbx, [rsp+0C0h+arg_10]
0x18005daae  add     rsp, 0A0h
0x18005dab5  pop     r15
0x18005dab7  pop     r14
0x18005dab9  pop     rdi
0x18005daba  pop     rsi
0x18005dabb  pop     rbp
0x18005dabc  retn
```
