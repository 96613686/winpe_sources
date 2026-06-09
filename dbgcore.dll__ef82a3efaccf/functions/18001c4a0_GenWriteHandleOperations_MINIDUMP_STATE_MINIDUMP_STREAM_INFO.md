# GenWriteHandleOperations(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *)

- ea: `0x18001c4a0`
- end: `0x18001c6d7`
- name: `?GenWriteHandleOperations@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x18001c4a0`
- `0x18002c010`

## string_xrefs

- `0x18001c4f2`: `GenWriteHandleOperations stream RVA overflow`
- `0x18001c53d`: `GenWriteHandleOperations.Seek(0x%x) failed, 0x%08x`
- `0x18001c61f`: `GenWriteHandleOperations.List.Write(0x%x) failed, 0x%08x`
- `0x18001c669`: `GenWriteHandleOperations.Ops.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall GenWriteHandleOperations(struct _MINIDUMP_STATE *a1, struct _MINIDUMP_STREAM_INFO *a2)
{
  unsigned int v5; // r14d
  int v6; // eax
  unsigned int v7; // esi
  __int64 v8; // rcx
  __int64 v9; // r9
  const char *v10; // r8
  int v11; // eax
  int v12; // ecx
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h] BYREF

  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( *((_QWORD *)a2 + 20) > 0xFFFFFFFF )
  {
    (*(void (__fastcall **)(_QWORD, __int64, const char *))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "GenWriteHandleOperations stream RVA overflow");
    return 2147942487LL;
  }
  v5 = *((_DWORD *)a2 + 40);
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 24LL))(
         *((_QWORD *)a1 + 3),
         0,
         v5,
         0);
  v7 = v6;
  if ( !v6 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *, char *, __int64 *))(**((_QWORD **)a1 + 2)
                                                                                              + 368LL))(
           *((_QWORD *)a1 + 2),
           *(_QWORD *)a1,
           *((unsigned int *)a1 + 2),
           &v13,
           (char *)&v15 + 8,
           &v14) )
    {
      return 0;
    }
    if ( !DWORD2(v15) )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 2) + 376LL))(*((_QWORD *)a1 + 2), v13);
      return 0;
    }
    if ( DWORD2(v15) > 0xE38E38 )
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 2) + 376LL))(*((_QWORD *)a1 + 2), v13);
      return 2147942934LL;
    }
    v8 = *((_QWORD *)a1 + 3);
    *(_QWORD *)&v15 = 0x12000000010LL;
    HIDWORD(v15) = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v8 + 32LL))(v8, &v15, 16);
    if ( v7 )
    {
      v9 = 16;
      v10 = "GenWriteHandleOperations.List.Write(0x%x) failed, 0x%08x";
    }
    else
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
             *((_QWORD *)a1 + 3),
             v14,
             (unsigned int)(288 * DWORD2(v15)));
      if ( !v7 )
      {
        v11 = DWORD2(v15);
        *((_DWORD *)a2 + 46) = v5;
        v12 = 288 * v11 + 16;
        *((_DWORD *)a2 + 47) = v12;
        *((_QWORD *)a2 + 20) = v5 + v12;
        goto LABEL_17;
      }
      v10 = "GenWriteHandleOperations.Ops.Write(0x%x) failed, 0x%08x";
      v9 = 288LL * DWORD2(v15);
    }
    (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      v10,
      v9,
      v7);
LABEL_17:
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)a1 + 2) + 376LL))(*((_QWORD *)a1 + 2), v13);
    return v7;
  }
  (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
    *((_QWORD *)a1 + 5),
    4,
    "GenWriteHandleOperations.Seek(0x%x) failed, 0x%08x",
    v5,
    v6);
  return v7;
}

```

## disassembly

```asm
0x18001c4a0  mov     [rsp-18h+arg_10], rbx
0x18001c4a5  mov     [rsp-18h+arg_18], rsi
0x18001c4aa  push    rbp
0x18001c4ab  push    rdi
0x18001c4ac  push    r14
0x18001c4ae  mov     rbp, rsp
0x18001c4b1  sub     rsp, 70h
0x18001c4b5  mov     rax, cs:__security_cookie
0x18001c4bc  xor     rax, rsp
0x18001c4bf  mov     [rbp+var_10], rax
0x18001c4c3  mov     eax, 0FFFFFFFFh
0x18001c4c8  mov     [rbp+var_30], 0
0x18001c4d0  xorps   xmm0, xmm0
0x18001c4d3  mov     rdi, rdx
0x18001c4d6  mov     rbx, rcx
0x18001c4d9  mov     [rbp+var_28], 0
0x18001c4e1  movups  [rbp+var_20], xmm0
0x18001c4e5  cmp     [rdx+0A0h], rax
0x18001c4ec  jbe     short loc_18001C514
0x18001c4ee  mov     rcx, [rcx+28h]
0x18001c4f2  lea     r8, aGenwritehandle_1; "GenWriteHandleOperations stream RVA ove"...
0x18001c4f9  mov     edx, 4
0x18001c4fe  mov     rax, [rcx]
0x18001c501  mov     rax, [rax+8]
0x18001c505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c50a  mov     eax, 80070057h
0x18001c50f  jmp     loc_18001C6B6
0x18001c514  mov     r14d, [rdx+0A0h]
0x18001c51b  xor     r9d, r9d
0x18001c51e  mov     rcx, [rcx+18h]
0x18001c522  mov     r8d, r14d
0x18001c525  xor     edx, edx
0x18001c527  mov     rax, [rcx]
0x18001c52a  mov     rax, [rax+18h]
0x18001c52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c533  mov     esi, eax
0x18001c535  test    eax, eax
0x18001c537  jz      short loc_18001C561
0x18001c539  mov     rcx, [rbx+28h]
0x18001c53d  lea     r8, aGenwritehandle; "GenWriteHandleOperations.Seek(0x%x) fai"...
0x18001c544  mov     r9d, r14d
0x18001c547  mov     dword ptr [rsp+70h+var_50], esi
0x18001c54b  mov     rdx, [rcx]
0x18001c54e  mov     rax, [rdx+8]
0x18001c552  mov     edx, 4
0x18001c557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c55c  jmp     loc_18001C6B4
0x18001c561  mov     rcx, [rbx+10h]
0x18001c565  lea     rdx, [rbp+var_28]
0x18001c569  mov     r8d, [rbx+8]
0x18001c56d  lea     r9, [rbp+var_30]
0x18001c571  mov     [rsp+70h+var_48], rdx
0x18001c576  lea     rdx, [rbp+var_20+8]
0x18001c57a  mov     [rsp+70h+var_50], rdx
0x18001c57f  mov     rax, [rcx]
0x18001c582  mov     rdx, [rbx]
0x18001c585  mov     rax, [rax+170h]
0x18001c58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c591  test    eax, eax
0x18001c593  jz      short loc_18001C59C
0x18001c595  xor     eax, eax
0x18001c597  jmp     loc_18001C6B6
0x18001c59c  mov     eax, dword ptr [rbp+var_20+8]
0x18001c59f  test    eax, eax
0x18001c5a1  jnz     short loc_18001C5BC
0x18001c5a3  mov     rcx, [rbx+10h]
0x18001c5a7  mov     rdx, [rbp+var_30]
0x18001c5ab  mov     rax, [rcx]
0x18001c5ae  mov     rax, [rax+178h]
0x18001c5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ba  jmp     short loc_18001C595
0x18001c5bc  cmp     eax, 0E38E38h
0x18001c5c1  jbe     short loc_18001C5E4
0x18001c5c3  mov     rcx, [rbx+10h]
0x18001c5c7  mov     rdx, [rbp+var_30]
0x18001c5cb  mov     rax, [rcx]
0x18001c5ce  mov     rax, [rax+178h]
0x18001c5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5da  mov     eax, 80070216h
0x18001c5df  jmp     loc_18001C6B6
0x18001c5e4  mov     rcx, [rbx+18h]
0x18001c5e8  lea     rdx, [rbp+var_20]
0x18001c5ec  mov     dword ptr [rbp+var_20], 10h
0x18001c5f3  mov     r8d, 10h
0x18001c5f9  mov     dword ptr [rbp+var_20+4], 120h
0x18001c600  mov     dword ptr [rbp+var_20+0Ch], 0
0x18001c607  mov     rax, [rcx]
0x18001c60a  mov     rax, [rax+20h]
0x18001c60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c613  mov     esi, eax
0x18001c615  test    eax, eax
0x18001c617  jz      short loc_18001C641
0x18001c619  mov     r9d, 10h
0x18001c61f  lea     r8, aGenwritehandle_12; "GenWriteHandleOperations.List.Write(0x%"...
0x18001c626  mov     rcx, [rbx+28h]
0x18001c62a  mov     dword ptr [rsp+70h+var_50], esi
0x18001c62e  mov     rdx, [rcx]
0x18001c631  mov     rax, [rdx+8]
0x18001c635  mov     edx, 4
0x18001c63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c63f  jmp     short loc_18001C69D
0x18001c641  mov     eax, dword ptr [rbp+var_20+8]
0x18001c644  mov     rcx, [rbx+18h]
0x18001c648  lea     r8d, [rax+rax*8]
0x18001c64c  mov     rdx, [rcx]
0x18001c64f  shl     r8d, 5
0x18001c653  mov     rax, [rdx+20h]
0x18001c657  mov     rdx, [rbp+var_28]
0x18001c65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c660  mov     esi, eax
0x18001c662  test    eax, eax
0x18001c664  jz      short loc_18001C67A
0x18001c666  mov     eax, dword ptr [rbp+var_20+8]
0x18001c669  lea     r8, aGenwritehandle_5; "GenWriteHandleOperations.Ops.Write(0x%x"...
0x18001c670  lea     r9, [rax+rax*8]
0x18001c674  shl     r9, 5
0x18001c678  jmp     short loc_18001C626
0x18001c67a  mov     eax, dword ptr [rbp+var_20+8]
0x18001c67d  mov     [rdi+0B8h], r14d
0x18001c684  lea     ecx, [rax+rax*8]
0x18001c687  shl     ecx, 5
0x18001c68a  add     ecx, 10h
0x18001c68d  mov     [rdi+0BCh], ecx
0x18001c693  add     ecx, r14d
0x18001c696  mov     [rdi+0A0h], rcx
0x18001c69d  mov     rcx, [rbx+10h]
0x18001c6a1  mov     rdx, [rbp+var_30]
0x18001c6a5  mov     rax, [rcx]
0x18001c6a8  mov     rax, [rax+178h]
0x18001c6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6b4  mov     eax, esi
0x18001c6b6  mov     rcx, [rbp+var_10]
0x18001c6ba  xor     rcx, rsp; StackCookie
0x18001c6bd  call    __security_check_cookie
0x18001c6c2  lea     r11, [rsp+70h+var_s0]
0x18001c6c7  mov     rbx, [r11+30h]
0x18001c6cb  mov     rsi, [r11+38h]
0x18001c6cf  mov     rsp, r11
0x18001c6d2  pop     r14
0x18001c6d4  pop     rdi
0x18001c6d5  pop     rbp
0x18001c6d6  retn
```
