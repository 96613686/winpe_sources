# PopulateXFFHeader(IHttpContext *,STBUFF *)

- ea: `0x180001dc8`
- end: `0x180001f9d`
- name: `?PopulateXFFHeader@@YAJPEAVIHttpContext@@PEAVSTBUFF@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct STBUFF *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180005ab8`

## callees

- `0x180001948`
- `0x180001a2c`
- `0x180001dc8`
- `0x180001fa4`
- `0x1800067c0`
- `0x180007010`

## import_xrefs

- `msvcrt!strchr` at `0x180001e9e`
- `msvcrt!strchr` at `0x180001e9e`
- `msvcrt!isspace` at `0x180001e79`
- `msvcrt!isspace` at `0x180001ed1`
- `msvcrt!isspace` at `0x180001e79`
- `msvcrt!isspace` at `0x180001ed1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001f6e`

## pseudocode

```c
__int64 __fastcall PopulateXFFHeader(struct IHttpContext *a1, struct STBUFF *a2)
{
  int appended; // esi
  char *v5; // rdi
  char *v6; // rbx
  __int64 v7; // rax
  char *v8; // r13
  signed int v9; // r14d
  __int64 v10; // rbx
  unsigned int v11; // r12d
  __int64 v12; // rax
  int v14; // [rsp+30h] [rbp-59h]
  int v15; // [rsp+34h] [rbp-55h] BYREF
  void *v16; // [rsp+38h] [rbp-51h] BYREF
  void **v17; // [rsp+40h] [rbp-49h] BYREF
  char *Str; // [rsp+48h] [rbp-41h]
  int v19; // [rsp+50h] [rbp-39h]
  char v20; // [rsp+5Ch] [rbp-2Dh] BYREF

  v16 = 0;
  v15 = 0;
  STBUFF::STBUFF((STBUFF *)&v17, (int)a2);
  if ( (*(int (__fastcall **)(struct IHttpContext *, const char *, void **, int *))(*(_QWORD *)a1 + 120LL))(
         a1,
         "HTTP_X_FORWARDED_FOR",
         &v16,
         &v15) >= 0 )
  {
    appended = STBUFF::AppendData((STBUFF *)&v17, v16, 0xFFFFFFFF, 0xFFFFFFFF);
    if ( appended >= 0 )
    {
      v14 = 0;
      Str[v19] = 0;
      Str[v19 + 1] = 0;
      v5 = Str;
      do
      {
        while ( isspace(*v5) || *v5 == 44 )
          ++v5;
        if ( !*v5 )
          break;
        v6 = strchr(v5, 44);
        if ( !v6 )
        {
          v14 = 1;
          v7 = -1;
          do
            ++v7;
          while ( v5[v7] );
          v6 = &v5[(int)v7];
        }
        v8 = v6;
        do
        {
          if ( v6 <= v5 )
            break;
          --v6;
        }
        while ( isspace(*v6) );
        v9 = (_DWORD)v6 - (_DWORD)v5 + 1;
        if ( v9 > 0 )
        {
          v10 = *((unsigned int *)a2 + 4);
          if ( (_DWORD)v10 )
          {
            v11 = v10 + 1;
            appended = STBUFF::Resize(a2, (int)v10 + 1);
            if ( appended < 0 )
              break;
            *(_BYTE *)(v10 + *((_QWORD *)a2 + 1)) = 44;
            v12 = *((_QWORD *)a2 + 1);
            *((_DWORD *)a2 + 4) = v11;
            *(_BYTE *)(v11 + v12) = 0;
            *(_BYTE *)((unsigned int)(*((_DWORD *)a2 + 4) + 1) + *((_QWORD *)a2 + 1)) = 0;
          }
          appended = STBUFF::AppendData(a2, v5, v9, 0xFFFFFFFF);
          if ( appended < 0 )
            break;
        }
        v5 = v8 + 1;
      }
      while ( !v14 );
    }
  }
  else
  {
    appended = 0;
  }
  v17 = &STBUFF::`vftable';
  if ( Str != &v20 )
    LocalFree(Str);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180001dc8  mov     [rsp-8+arg_10], rbx
0x180001dcd  push    rbp
0x180001dce  push    rsi
0x180001dcf  push    rdi
0x180001dd0  push    r12
0x180001dd2  push    r13
0x180001dd4  push    r14
0x180001dd6  push    r15
0x180001dd8  lea     rbp, [rsp-27h]
0x180001ddd  sub     rsp, 0B0h
0x180001de4  mov     rax, cs:__security_cookie
0x180001deb  xor     rax, rsp
0x180001dee  mov     [rbp+57h+var_40], rax
0x180001df2  mov     rbx, rcx
0x180001df5  xor     r12d, r12d
0x180001df8  lea     rcx, [rbp+57h+var_A0]; this
0x180001dfc  mov     [rbp+57h+var_A8], r12
0x180001e00  mov     [rbp+57h+var_AC], r12d
0x180001e04  mov     r15, rdx
0x180001e07  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180001e0c  mov     rax, [rbx]
0x180001e0f  lea     r9, [rbp+57h+var_AC]
0x180001e13  lea     r8, [rbp+57h+var_A8]
0x180001e17  mov     rcx, rbx
0x180001e1a  lea     rdx, aHttpXForwarded; "HTTP_X_FORWARDED_FOR"
0x180001e21  mov     rax, [rax+78h]
0x180001e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e2a  test    eax, eax
0x180001e2c  jns     short loc_180001E36
0x180001e2e  mov     esi, r12d
0x180001e31  jmp     loc_180001F56
0x180001e36  mov     rdx, [rbp+57h+var_A8]; void *
0x180001e3a  lea     rcx, [rbp+57h+var_A0]; this
0x180001e3e  or      eax, 0FFFFFFFFh
0x180001e41  mov     r9d, eax; unsigned int
0x180001e44  mov     r8d, eax; unsigned int
0x180001e47  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180001e4c  mov     esi, eax
0x180001e4e  test    eax, eax
0x180001e50  js      loc_180001F56
0x180001e56  mov     edx, [rbp+57h+var_90]
0x180001e59  mov     rcx, [rbp+57h+Str]
0x180001e5d  mov     [rbp+57h+var_B0], r12d
0x180001e61  mov     [rdx+rcx], r12b
0x180001e65  mov     edx, [rbp+57h+var_90]
0x180001e68  mov     rcx, [rbp+57h+Str]
0x180001e6c  inc     edx
0x180001e6e  mov     [rdx+rcx], r12b
0x180001e72  mov     rdi, [rbp+57h+Str]
0x180001e76  movsx   ecx, byte ptr [rdi]; C
0x180001e79  call    cs:__imp_isspace
0x180001e7f  test    eax, eax
0x180001e81  jnz     short loc_180001E89
0x180001e83  mov     al, [rdi]
0x180001e85  cmp     al, 2Ch ; ','
0x180001e87  jnz     short loc_180001E8E
0x180001e89  inc     rdi
0x180001e8c  jmp     short loc_180001E76
0x180001e8e  test    al, al
0x180001e90  jz      loc_180001F56
0x180001e96  mov     edx, 2Ch ; ','; Val
0x180001e9b  mov     rcx, rdi; Str
0x180001e9e  call    cs:__imp_strchr
0x180001ea4  mov     rbx, rax
0x180001ea7  test    rax, rax
0x180001eaa  jnz     short loc_180001EC6
0x180001eac  mov     [rbp+57h+var_B0], 1
0x180001eb3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001eb7  inc     rax
0x180001eba  cmp     [rdi+rax], r12b
0x180001ebe  jnz     short loc_180001EB7
0x180001ec0  movsxd  rbx, eax
0x180001ec3  add     rbx, rdi
0x180001ec6  mov     r13, rbx
0x180001ec9  jmp     short loc_180001EDB
0x180001ecb  dec     rbx
0x180001ece  movsx   ecx, byte ptr [rbx]; C
0x180001ed1  call    cs:__imp_isspace
0x180001ed7  test    eax, eax
0x180001ed9  jz      short loc_180001EE0
0x180001edb  cmp     rbx, rdi
0x180001ede  ja      short loc_180001ECB
0x180001ee0  sub     ebx, edi
0x180001ee2  lea     r14d, [rbx+1]
0x180001ee6  test    r14d, r14d
0x180001ee9  jle     short loc_180001F48
0x180001eeb  mov     ebx, [r15+10h]
0x180001eef  test    ebx, ebx
0x180001ef1  jz      short loc_180001F30
0x180001ef3  lea     r12d, [rbx+1]
0x180001ef7  mov     rcx, r15; this
0x180001efa  mov     edx, r12d; unsigned int
0x180001efd  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x180001f02  mov     esi, eax
0x180001f04  test    eax, eax
0x180001f06  js      short loc_180001F56
0x180001f08  mov     rax, [r15+8]
0x180001f0c  mov     ecx, r12d
0x180001f0f  mov     byte ptr [rbx+rax], 2Ch ; ','
0x180001f13  mov     rax, [r15+8]
0x180001f17  mov     [r15+10h], r12d
0x180001f1b  xor     r12d, r12d
0x180001f1e  mov     [rcx+rax], r12b
0x180001f22  mov     ecx, [r15+10h]
0x180001f26  mov     rax, [r15+8]
0x180001f2a  inc     ecx
0x180001f2c  mov     [rcx+rax], r12b
0x180001f30  or      r9d, 0FFFFFFFFh; unsigned int
0x180001f34  mov     r8d, r14d; unsigned int
0x180001f37  mov     rdx, rdi; void *
0x180001f3a  mov     rcx, r15; this
0x180001f3d  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180001f42  mov     esi, eax
0x180001f44  test    eax, eax
0x180001f46  js      short loc_180001F56
0x180001f48  lea     rdi, [r13+1]
0x180001f4c  cmp     [rbp+57h+var_B0], r12d
0x180001f50  jz      loc_180001E76
0x180001f56  mov     rcx, [rbp+57h+Str]; hMem
0x180001f5a  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180001f61  mov     [rbp+57h+var_A0], rax
0x180001f65  lea     rax, [rbp+57h+var_84]
0x180001f69  cmp     rcx, rax
0x180001f6c  jz      short loc_180001F74
0x180001f6e  call    cs:__imp_LocalFree
0x180001f74  mov     eax, esi
0x180001f76  mov     rcx, [rbp+57h+var_40]
0x180001f7a  xor     rcx, rsp; StackCookie
0x180001f7d  call    __security_check_cookie
0x180001f82  mov     rbx, [rsp+0E0h+arg_10]
0x180001f8a  add     rsp, 0B0h
0x180001f91  pop     r15
0x180001f93  pop     r14
0x180001f95  pop     r13
0x180001f97  pop     r12
0x180001f99  pop     rdi
0x180001f9a  pop     rsi
0x180001f9b  pop     rbp
0x180001f9c  retn
```
