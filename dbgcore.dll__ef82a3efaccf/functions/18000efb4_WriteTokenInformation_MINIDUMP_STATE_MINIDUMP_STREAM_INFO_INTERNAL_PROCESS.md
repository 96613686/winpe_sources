# WriteTokenInformation(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000efb4`
- end: `0x18000f17a`
- name: `?WriteTokenInformation@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x18000bcbc`
- `0x18000efb4`
- `0x18002c010`

## string_xrefs

- `0x18000f01c`: `WriteTokenInformation.Write(0x%x,%d,%d) failed, 0x%08x`
- `0x18000f089`: `WriteTokenInformation.ProcessToken(%d,%d) failed, 0x%08x`
- `0x18000f0ec`: `WriteTokenInformation.ThreadToken(%d,%d) failed, 0x%08x`
- `0x18000f144`: `WriteTokenInformation.Write(%d,%d)(%d,%d) error.`

## pseudocode

```c
__int64 __fastcall WriteTokenInformation(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  int v3; // r15d
  int v5; // eax
  unsigned int v6; // edx
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int *v10; // rdi
  int v11; // ebp
  unsigned int v12; // eax
  char *v13; // rsi
  char *v14; // rdi
  unsigned int *v15; // r14
  unsigned int v16; // eax
  __int64 v18; // [rsp+20h] [rbp-78h]
  __int64 v19; // [rsp+28h] [rbp-70h]
  __int64 v20; // [rsp+30h] [rbp-68h]
  unsigned int v21; // [rsp+40h] [rbp-58h] BYREF
  int v22; // [rsp+44h] [rbp-54h]
  int v23; // [rsp+48h] [rbp-50h]
  int v24; // [rsp+4Ch] [rbp-4Ch]

  v3 = 16;
  v21 = *((_DWORD *)a2 + 49);
  v5 = *((_DWORD *)a2 + 50);
  v6 = *((_DWORD *)a2 + 48);
  v22 = v5;
  v23 = 16;
  v24 = 72;
  v8 = WriteAtOffset(a1, v6, &v21, 0x10u);
  v9 = v8;
  if ( v8 )
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "WriteTokenInformation.Write(0x%x,%d,%d) failed, 0x%08x",
      16,
      v21,
      v22,
      v8);
  if ( v22 )
  {
    v10 = (unsigned int *)*((_QWORD *)a3 + 9143);
    if ( v10 )
    {
      v11 = 1;
      v3 = *v10 + 16;
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
              *((_QWORD *)a1 + 3),
              *((_QWORD *)a3 + 9143));
      v9 = v12;
      if ( v12 )
      {
        LODWORD(v19) = v12;
        LODWORD(v18) = v10[1];
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
          *((_QWORD *)a1 + 5),
          4,
          "WriteTokenInformation.ProcessToken(%d,%d) failed, 0x%08x",
          *v10,
          v18,
          v19);
      }
    }
    else
    {
      v11 = 0;
    }
    v13 = (char *)a3 + 104;
    v14 = (char *)*((_QWORD *)a3 + 13);
    while ( v14 != v13 )
    {
      v15 = (unsigned int *)*((_QWORD *)v14 + 2);
      v14 = *(char **)v14;
      if ( v15 )
      {
        ++v11;
        v3 += *v15;
        v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, _QWORD))(**((_QWORD **)a1 + 3) + 32LL))(
                *((_QWORD *)a1 + 3),
                v15,
                *v15);
        v9 = v16;
        if ( v16 )
        {
          LODWORD(v19) = v16;
          LODWORD(v18) = v15[1];
          (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
            *((_QWORD *)a1 + 5),
            4,
            "WriteTokenInformation.ThreadToken(%d,%d) failed, 0x%08x",
            *v15,
            v18,
            v19);
        }
      }
    }
    if ( v11 != v22 || v3 != v21 )
    {
      LODWORD(v20) = v11;
      LODWORD(v19) = v3;
      LODWORD(v18) = v22;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "WriteTokenInformation.Write(%d,%d)(%d,%d) error.",
        v21,
        v18,
        v19,
        v20);
      return (unsigned int)-2147024883;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18000efb4  push    rbx
0x18000efb6  push    rbp
0x18000efb7  push    rsi
0x18000efb8  push    rdi
0x18000efb9  push    r13
0x18000efbb  push    r14
0x18000efbd  push    r15
0x18000efbf  sub     rsp, 60h
0x18000efc3  mov     rax, cs:__security_cookie
0x18000efca  xor     rax, rsp
0x18000efcd  mov     [rsp+98h+var_48], rax
0x18000efd2  mov     eax, [rdx+0C4h]
0x18000efd8  mov     r15d, 10h
0x18000efde  mov     [rsp+98h+var_58], eax
0x18000efe2  mov     r14, r8
0x18000efe5  mov     eax, [rdx+0C8h]
0x18000efeb  lea     r8, [rsp+98h+var_58]; void *
0x18000eff0  mov     edx, [rdx+0C0h]; unsigned int
0x18000eff6  mov     r9d, r15d; unsigned int
0x18000eff9  mov     r13, rcx
0x18000effc  mov     [rsp+98h+var_54], eax
0x18000f000  mov     [rsp+98h+var_50], r15d
0x18000f005  mov     [rsp+98h+var_4C], 48h ; 'H'
0x18000f00d  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000f012  mov     ebx, eax
0x18000f014  test    eax, eax
0x18000f016  jz      short loc_18000F04A
0x18000f018  mov     rcx, [r13+28h]
0x18000f01c  lea     r8, aWritetokeninfo; "WriteTokenInformation.Write(0x%x,%d,%d)"...
0x18000f023  mov     [rsp+98h+var_68], ebx
0x18000f027  mov     r9d, r15d
0x18000f02a  mov     rdx, [rcx]
0x18000f02d  mov     rax, [rdx+8]
0x18000f031  mov     edx, [rsp+98h+var_54]
0x18000f035  mov     dword ptr [rsp+98h+var_70], edx
0x18000f039  mov     edx, [rsp+98h+var_58]
0x18000f03d  mov     dword ptr [rsp+98h+var_78], edx
0x18000f041  lea     edx, [r15-0Ch]
0x18000f045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f04a  cmp     [rsp+98h+var_54], 0
0x18000f04f  jz      loc_18000F15C
0x18000f055  mov     rdi, [r14+11DB8h]
0x18000f05c  test    rdi, rdi
0x18000f05f  jz      short loc_18000F0B0
0x18000f061  mov     rcx, [r13+18h]
0x18000f065  mov     rdx, rdi
0x18000f068  mov     r8d, [rdi]
0x18000f06b  mov     ebp, 1
0x18000f070  mov     rax, [rcx]
0x18000f073  lea     r15d, [r8+10h]
0x18000f077  mov     rax, [rax+20h]
0x18000f07b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f080  mov     ebx, eax
0x18000f082  test    eax, eax
0x18000f084  jz      short loc_18000F0B2
0x18000f086  mov     edx, [rdi+4]
0x18000f089  lea     r8, aWritetokeninfo_2; "WriteTokenInformation.ProcessToken(%d,%"...
0x18000f090  mov     rcx, [r13+28h]
0x18000f094  mov     r9d, [rdi]
0x18000f097  mov     dword ptr [rsp+98h+var_70], ebx
0x18000f09b  mov     dword ptr [rsp+98h+var_78], edx
0x18000f09f  lea     edx, [rbp+3]
0x18000f0a2  mov     rax, [rcx]
0x18000f0a5  mov     rax, [rax+8]
0x18000f0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ae  jmp     short loc_18000F0B2
0x18000f0b0  xor     ebp, ebp
0x18000f0b2  lea     rsi, [r14+68h]
0x18000f0b6  mov     rdi, [rsi]
0x18000f0b9  jmp     short loc_18000F113
0x18000f0bb  mov     r14, [rdi+10h]
0x18000f0bf  mov     rdi, [rdi]
0x18000f0c2  test    r14, r14
0x18000f0c5  jz      short loc_18000F113
0x18000f0c7  mov     rcx, [r13+18h]
0x18000f0cb  mov     rdx, r14
0x18000f0ce  mov     r8d, [r14]
0x18000f0d1  inc     ebp
0x18000f0d3  add     r15d, [r14]
0x18000f0d6  mov     rax, [rcx]
0x18000f0d9  mov     rax, [rax+20h]
0x18000f0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e2  mov     ebx, eax
0x18000f0e4  test    eax, eax
0x18000f0e6  jz      short loc_18000F113
0x18000f0e8  mov     edx, [r14+4]
0x18000f0ec  lea     r8, aWritetokeninfo_1; "WriteTokenInformation.ThreadToken(%d,%d"...
0x18000f0f3  mov     rcx, [r13+28h]
0x18000f0f7  mov     r9d, [r14]
0x18000f0fa  mov     dword ptr [rsp+98h+var_70], ebx
0x18000f0fe  mov     dword ptr [rsp+98h+var_78], edx
0x18000f102  mov     edx, 4
0x18000f107  mov     rax, [rcx]
0x18000f10a  mov     rax, [rax+8]
0x18000f10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f113  cmp     rdi, rsi
0x18000f116  jnz     short loc_18000F0BB
0x18000f118  mov     r9d, [rsp+98h+var_58]
0x18000f11d  cmp     ebp, [rsp+98h+var_54]
0x18000f121  jnz     short loc_18000F128
0x18000f123  cmp     r15d, r9d
0x18000f126  jz      short loc_18000F15C
0x18000f128  mov     r8d, [rsp+98h+var_54]
0x18000f12d  mov     edx, 4
0x18000f132  mov     rcx, [r13+28h]
0x18000f136  mov     [rsp+98h+var_68], ebp
0x18000f13a  mov     dword ptr [rsp+98h+var_70], r15d
0x18000f13f  mov     dword ptr [rsp+98h+var_78], r8d
0x18000f144  lea     r8, aWritetokeninfo_0; "WriteTokenInformation.Write(%d,%d)(%d,%"...
0x18000f14b  mov     rax, [rcx]
0x18000f14e  mov     rax, [rax+8]
0x18000f152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f157  mov     ebx, 8007000Dh
0x18000f15c  mov     eax, ebx
0x18000f15e  mov     rcx, [rsp+98h+var_48]
0x18000f163  xor     rcx, rsp; StackCookie
0x18000f166  call    __security_check_cookie
0x18000f16b  add     rsp, 60h
0x18000f16f  pop     r15
0x18000f171  pop     r14
0x18000f173  pop     r13
0x18000f175  pop     rdi
0x18000f176  pop     rsi
0x18000f177  pop     rbp
0x18000f178  pop     rbx
0x18000f179  retn
```
