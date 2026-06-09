# CTxtEdit::InsertFromFile(ushort const *)

- ea: `0x18005c250`
- end: `0x18005c447`
- name: `?InsertFromFile@CTxtEdit@@AEAA_JPEBG@Z`
- size: `503`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005c854`

## callees

- `0x180041adc`
- `0x18005c250`
- `0x1800907ac`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## string_xrefs

- `0x18005c301`: `OleCreateLinkToFile`

## pseudocode

```c
__int64 __fastcall CTxtEdit::InsertFromFile(CTxtEdit *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rdi
  int v6; // ebx
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v8)(const unsigned __int16 *, GUID *, __int64); // rbx
  _DWORD v10[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v11[16]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v12; // [rsp+58h] [rbp-11h]
  __int64 v13; // [rsp+60h] [rbp-9h] BYREF
  __int64 v14; // [rsp+68h] [rbp-1h] BYREF
  int v15; // [rsp+78h] [rbp+Fh]

  memset_0(v10, 0, 0x48u);
  v4 = *((_QWORD *)this + 17);
  if ( !v4 )
    return -2147467262;
  v5 = *(_QWORD *)(v4 + 32);
  if ( !v5 )
    return -2147467262;
  v10[0] = 72;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 24LL))(v5, &v13);
  if ( !v6 )
  {
    v6 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 1) + 24LL))((char *)this + 8, &v14);
    if ( v14 )
    {
      Ole32Procs = CThreadData::GetOle32Procs();
      v8 = (__int64 (__fastcall **)(const unsigned __int16 *, GUID *, __int64))((char *)Ole32Procs + 88);
      if ( !*((_QWORD *)Ole32Procs + 11) )
        SetProcAddr((FARPROC *)Ole32Procs + 11, 1, "OleCreateLinkToFile");
      if ( *v8 )
      {
        v6 = (*v8)(a2, &IID_IOleObject, 1);
        if ( !v6 )
        {
          v15 = 1;
          v10[1] = -1;
          v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 120LL))(v12, v11);
          if ( !v6 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)v5 + 48LL))(
                   v5,
                   v11,
                   v13,
                   0xFFFFFFFFLL);
            if ( !v6 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, v14);
              if ( !v6 )
                v6 = (*(__int64 (__fastcall **)(char *, _DWORD *))(*((_QWORD *)this + 1) + 56LL))((char *)this + 8, v10);
            }
          }
        }
      }
      else
      {
        v6 = -2147467259;
      }
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v6;
}

```

## disassembly

```asm
0x18005c250  mov     [rsp-8+arg_10], rbx
0x18005c255  push    rbp
0x18005c256  push    rsi
0x18005c257  push    rdi
0x18005c258  push    r14
0x18005c25a  push    r15
0x18005c25c  lea     rbp, [rsp-37h]
0x18005c261  sub     rsp, 0A0h
0x18005c268  mov     rax, cs:__security_cookie
0x18005c26f  xor     rax, rsp
0x18005c272  mov     [rbp+57h+var_30], rax
0x18005c276  mov     r15, rdx
0x18005c279  mov     rsi, rcx
0x18005c27c  mov     ebx, 48h ; 'H'
0x18005c281  lea     rcx, [rbp+57h+var_80]; void *
0x18005c285  mov     r8d, ebx; Size
0x18005c288  xor     edx, edx; Val
0x18005c28a  call    memset_0
0x18005c28f  mov     rdi, [rsi+88h]
0x18005c296  test    rdi, rdi
0x18005c299  jz      loc_18005C41D
0x18005c29f  mov     rdi, [rdi+20h]
0x18005c2a3  test    rdi, rdi
0x18005c2a6  jz      loc_18005C41D
0x18005c2ac  mov     [rbp+57h+var_80], ebx
0x18005c2af  lea     rdx, [rbp+57h+var_60]
0x18005c2b3  mov     rax, [rdi]
0x18005c2b6  mov     rcx, rdi
0x18005c2b9  mov     rax, [rax+18h]
0x18005c2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2c2  mov     ebx, eax
0x18005c2c4  test    eax, eax
0x18005c2c6  jnz     loc_18005C3D9
0x18005c2cc  mov     rax, [rsi+8]
0x18005c2d0  lea     rdx, [rbp+57h+var_58]
0x18005c2d4  lea     rcx, [rsi+8]
0x18005c2d8  mov     rax, [rax+18h]
0x18005c2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c2e1  cmp     [rbp+57h+var_58], 0
0x18005c2e6  mov     ebx, eax
0x18005c2e8  jz      loc_18005C3D9
0x18005c2ee  mov     r14, [rbp+57h+var_60]
0x18005c2f2  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18005c2f7  lea     rbx, [rax+58h]
0x18005c2fb  cmp     qword ptr [rbx], 0
0x18005c2ff  jnz     short loc_18005C315
0x18005c301  lea     r8, aOlecreatelinkt; "OleCreateLinkToFile"
0x18005c308  mov     edx, 1
0x18005c30d  mov     rcx, rbx
0x18005c310  call    SetProcAddr
0x18005c315  mov     rax, [rbx]
0x18005c318  test    rax, rax
0x18005c31b  jz      loc_18005C3D4
0x18005c321  xor     r9d, r9d
0x18005c324  lea     rcx, [rbp+57h+var_68]
0x18005c328  mov     [rsp+0C0h+var_90], rcx
0x18005c32d  lea     rdx, IID_IOleObject
0x18005c334  mov     [rsp+0C0h+var_98], r14
0x18005c339  mov     rcx, r15
0x18005c33c  mov     [rsp+0C0h+var_A0], 0
0x18005c345  lea     r8d, [r9+1]
0x18005c349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c34e  mov     ebx, eax
0x18005c350  test    eax, eax
0x18005c352  jnz     loc_18005C3D9
0x18005c358  mov     rcx, [rbp+57h+var_68]
0x18005c35c  lea     rdx, [rbp+57h+var_78]
0x18005c360  mov     [rbp+57h+var_48], 1
0x18005c367  or      r14d, 0FFFFFFFFh
0x18005c36b  mov     [rbp+57h+var_7C], r14d
0x18005c36f  mov     rax, [rcx]
0x18005c372  mov     rax, [rax+78h]
0x18005c376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c37b  mov     ebx, eax
0x18005c37d  test    eax, eax
0x18005c37f  jnz     short loc_18005C3D9
0x18005c381  mov     rax, [rdi]
0x18005c384  lea     rdx, [rbp+57h+var_78]
0x18005c388  mov     r8, [rbp+57h+var_60]
0x18005c38c  mov     r9d, r14d
0x18005c38f  mov     rcx, rdi
0x18005c392  mov     rax, [rax+30h]
0x18005c396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c39b  mov     ebx, eax
0x18005c39d  test    eax, eax
0x18005c39f  jnz     short loc_18005C3D9
0x18005c3a1  mov     rcx, [rbp+57h+var_68]
0x18005c3a5  mov     rdx, [rbp+57h+var_58]
0x18005c3a9  mov     rax, [rcx]
0x18005c3ac  mov     rax, [rax+18h]
0x18005c3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3b5  mov     ebx, eax
0x18005c3b7  test    eax, eax
0x18005c3b9  jnz     short loc_18005C3D9
0x18005c3bb  mov     rax, [rsi+8]
0x18005c3bf  lea     rdx, [rbp+57h+var_80]
0x18005c3c3  lea     rcx, [rsi+8]
0x18005c3c7  mov     rax, [rax+38h]
0x18005c3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3d0  mov     ebx, eax
0x18005c3d2  jmp     short loc_18005C3D9
0x18005c3d4  mov     ebx, 80004005h
0x18005c3d9  mov     rcx, [rbp+57h+var_68]
0x18005c3dd  test    rcx, rcx
0x18005c3e0  jz      short loc_18005C3EE
0x18005c3e2  mov     rax, [rcx]
0x18005c3e5  mov     rax, [rax+10h]
0x18005c3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c3ee  mov     rcx, [rbp+57h+var_58]
0x18005c3f2  test    rcx, rcx
0x18005c3f5  jz      short loc_18005C403
0x18005c3f7  mov     rax, [rcx]
0x18005c3fa  mov     rax, [rax+10h]
0x18005c3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c403  mov     rcx, [rbp+57h+var_60]
0x18005c407  test    rcx, rcx
0x18005c40a  jz      short loc_18005C418
0x18005c40c  mov     rax, [rcx]
0x18005c40f  mov     rax, [rax+10h]
0x18005c413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c418  movsxd  rax, ebx
0x18005c41b  jmp     short loc_18005C424
0x18005c41d  mov     rax, 0FFFFFFFF80004002h
0x18005c424  mov     rcx, [rbp+57h+var_30]
0x18005c428  xor     rcx, rsp; StackCookie
0x18005c42b  call    __security_check_cookie
0x18005c430  mov     rbx, [rsp+0C0h+arg_10]
0x18005c438  add     rsp, 0A0h
0x18005c43f  pop     r15
0x18005c441  pop     r14
0x18005c443  pop     rdi
0x18005c444  pop     rsi
0x18005c445  pop     rbp
0x18005c446  retn
```
