# CNtfsSTATSTGArray::NextAt(ulong,tagSTATSTG *,ulong *)

- ea: `0x180053fb8`
- end: `0x1800541d3`
- name: `?NextAt@CNtfsSTATSTGArray@@QEAAJKPEAUtagSTATSTG@@PEAK@Z`
- size: `539`
- prototype: `__int64 __fastcall(CNtfsSTATSTGArray *__hidden this, unsigned int, struct tagSTATSTG *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180053f20`

## callees

- `0x18001e2f0`
- `0x180053fb8`
- `0x180058e60`
- `0x180058e8c`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18005404d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18005404d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800540bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800540bf`

## pseudocode

```c
__int64 __fastcall CNtfsSTATSTGArray::NextAt(
        CNtfsSTATSTGArray *this,
        unsigned int a2,
        struct tagSTATSTG *a3,
        unsigned int *a4)
{
  CNtfsSTATSTGArray *v4; // rbx
  unsigned int v5; // r14d
  unsigned int v8; // ebp
  const struct _FILE_STREAM_INFORMATION *v9; // rsi
  unsigned int v10; // r12d
  unsigned int v11; // eax
  unsigned __int64 v12; // rbx
  void *v13; // rax
  size_t v14; // rbx
  __int64 v15; // rbx
  int v16; // r11d
  bool v17; // zf
  unsigned int v19; // [rsp+20h] [rbp-58h]
  const wchar_t *Src; // [rsp+28h] [rbp-50h]
  SIZE_T v21; // [rsp+30h] [rbp-48h]
  unsigned int v23; // [rsp+88h] [rbp+10h]

  v23 = a2;
  v4 = this;
  v5 = a2;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1), 0xFFFFFFFFLL);
  v8 = 1;
  if ( v5 < *((_DWORD *)v4 + 6) )
  {
    v9 = (const struct _FILE_STREAM_INFORMATION *)*((_QWORD *)v4 + 2);
    v10 = 0;
    v19 = 0;
    while ( v9 && v10 < *a4 )
    {
      if ( v9->StreamNameLength >= 0xC
        && !(unsigned int)_o__wcsnicmp(
                            (char *)&v9->StreamSize.QuadPart + 2 * ((unsigned __int64)v9->StreamNameLength >> 1) + 4,
                            L":$DATA",
                            6)
        && !(unsigned int)IsSpecifiedStream(v9, L"{4c8cc155-6c1e-11d1-8e41-00c04fb9386d}") )
      {
        v11 = v19++;
        if ( v5 <= v11 )
        {
          if ( v9->StreamNameLength == 14 )
          {
            LODWORD(v12) = 8;
            Src = L"CONTENTS";
          }
          else
          {
            Src = &v9->StreamName[1];
            v12 = (unsigned __int64)(v9->StreamNameLength - 14) >> 1;
          }
          v21 = (unsigned int)(2 * v12 + 2);
          v13 = CoTaskMemAlloc(v21);
          *((_QWORD *)a3 + 10 * v10) = v13;
          if ( !v13 )
          {
            v8 = -2147287032;
            goto LABEL_23;
          }
          v14 = 2LL * (unsigned int)v12;
          memcpy_0(v13, Src, v14);
          *(_WORD *)(v14 + *((_QWORD *)a3 + 10 * v10)) = 0;
          v15 = *((_QWORD *)a3 + 10 * v10);
          if ( (unsigned int)IsDocfileStream((const unsigned __int16 *)v15) )
          {
            StringCbCopyW((unsigned __int16 *)v15, v21, (const unsigned __int16 *)(v15 + 10));
            v16 = 1;
          }
          else
          {
            v16 = 2;
          }
          *((_DWORD *)a3 + 20 * v10 + 2) = v16;
          *((_QWORD *)a3 + 10 * v10 + 2) = v9->StreamSize.QuadPart;
          *((_QWORD *)a3 + 10 * v10 + 5) = 0;
          *((_QWORD *)a3 + 10 * v10 + 4) = 0;
          *((_QWORD *)a3 + 10 * v10 + 3) = 0;
          *((_QWORD *)a3 + 10 * v10 + 6) = 0;
          *((_DWORD *)a3 + 20 * v10 + 18) = 0;
          *((_DWORD *)a3 + 20 * v10 + 19) = 0;
          *(GUID *)((char *)a3 + 80 * v10 + 56) = GUID_NULL;
          v5 = ++v23;
          ++v10;
        }
      }
      if ( v9->NextEntryOffset )
        v9 = (const struct _FILE_STREAM_INFORMATION *)((char *)v9 + v9->NextEntryOffset);
      else
        v9 = 0;
    }
    v17 = v10 == *a4;
    *a4 = v10;
    v8 = !v17;
LABEL_23:
    v4 = this;
  }
  else
  {
    *a4 = 0;
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 32LL))(*((_QWORD *)v4 + 1));
  return v8;
}

```

## disassembly

```asm
0x180053fb8  mov     [rsp+arg_10], rbx
0x180053fbd  mov     [rsp+arg_8], edx
0x180053fc1  mov     [rsp+arg_0], rcx
0x180053fc6  push    rbp
0x180053fc7  push    rsi
0x180053fc8  push    rdi
0x180053fc9  push    r12
0x180053fcb  push    r13
0x180053fcd  push    r14
0x180053fcf  push    r15
0x180053fd1  sub     rsp, 40h
0x180053fd5  mov     rbx, rcx
0x180053fd8  mov     r14d, edx
0x180053fdb  mov     rcx, [rcx+8]
0x180053fdf  or      edx, 0FFFFFFFFh
0x180053fe2  mov     r13, r9
0x180053fe5  mov     r15, r8
0x180053fe8  mov     rax, [rcx]
0x180053feb  mov     rax, [rax+18h]
0x180053fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ff4  xor     edi, edi
0x180053ff6  mov     ebp, 1
0x180053ffb  cmp     r14d, [rbx+18h]
0x180053fff  jb      short loc_18005400A
0x180054001  mov     [r13+0], edi
0x180054005  jmp     loc_1800541A9
0x18005400a  mov     rsi, [rbx+10h]
0x18005400e  mov     r12d, edi
0x180054011  mov     [rsp+78h+var_58], edi
0x180054015  test    rsi, rsi
0x180054018  jz      loc_180054193
0x18005401e  cmp     r12d, [r13+0]
0x180054022  jnb     loc_180054193
0x180054028  cmp     dword ptr [rsi+4], 0Ch
0x18005402c  jb      loc_180054176
0x180054032  mov     eax, [rsi+4]
0x180054035  lea     rdx, aData; ":$DATA"
0x18005403c  shr     rax, 1
0x18005403f  mov     r8d, 6
0x180054045  add     rax, 6
0x180054049  lea     rcx, [rsi+rax*2]
0x18005404d  call    cs:__imp__o__wcsnicmp
0x180054053  test    eax, eax
0x180054055  jnz     loc_180054176
0x18005405b  lea     rdx, a4c8cc1556c1e11; "{4c8cc155-6c1e-11d1-8e41-00c04fb9386d}"
0x180054062  mov     rcx, rsi; struct _FILE_STREAM_INFORMATION *
0x180054065  call    ?IsSpecifiedStream@@YAHPEBU_FILE_STREAM_INFORMATION@@PEBG@Z; IsSpecifiedStream(_FILE_STREAM_INFORMATION const *,ushort const *)
0x18005406a  test    eax, eax
0x18005406c  jnz     loc_180054176
0x180054072  mov     ecx, [rsp+78h+var_58]
0x180054076  mov     eax, ecx
0x180054078  add     ecx, ebp
0x18005407a  mov     [rsp+78h+var_58], ecx
0x18005407e  cmp     r14d, eax
0x180054081  ja      loc_180054176
0x180054087  mov     eax, [rsi+4]
0x18005408a  add     eax, 0FFFFFFF2h
0x18005408d  jnz     short loc_1800540A2
0x18005408f  lea     rax, aContents; "CONTENTS"
0x180054096  mov     ebx, 8
0x18005409b  mov     [rsp+78h+Src], rax
0x1800540a0  jmp     short loc_1800540B1
0x1800540a2  lea     rcx, [rsi+1Ah]
0x1800540a6  movsxd  rbx, eax
0x1800540a9  mov     [rsp+78h+Src], rcx
0x1800540ae  shr     rbx, 1
0x1800540b1  lea     eax, ds:2[rbx*2]
0x1800540b8  mov     ecx, eax; cb
0x1800540ba  mov     [rsp+78h+var_48], rax
0x1800540bf  call    cs:__imp_CoTaskMemAlloc
0x1800540c5  mov     ecx, r12d
0x1800540c8  lea     r14, [rcx+rcx*4]
0x1800540cc  add     r14, r14
0x1800540cf  mov     [r15+r14*8], rax
0x1800540d3  test    rax, rax
0x1800540d6  jz      loc_18005418C
0x1800540dc  mov     rdx, [rsp+78h+Src]; Src
0x1800540e1  mov     ecx, ebx
0x1800540e3  lea     rbx, [rcx+rcx]
0x1800540e7  mov     rcx, rax; void *
0x1800540ea  mov     r8, rbx; Size
0x1800540ed  call    memcpy_0
0x1800540f2  mov     rax, [r15+r14*8]
0x1800540f6  mov     [rbx+rax], di
0x1800540fa  mov     rbx, [r15+r14*8]
0x1800540fe  mov     rcx, rbx; unsigned __int16 *
0x180054101  call    ?IsDocfileStream@@YAHPEBG@Z; IsDocfileStream(ushort const *)
0x180054106  test    eax, eax
0x180054108  jz      short loc_180054120
0x18005410a  mov     rdx, [rsp+78h+var_48]; unsigned __int64
0x18005410f  lea     r8, [rbx+0Ah]; unsigned __int16 *
0x180054113  mov     rcx, rbx; unsigned __int16 *
0x180054116  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18005411b  mov     r11d, ebp
0x18005411e  jmp     short loc_180054126
0x180054120  mov     r11d, 2
0x180054126  mov     [r15+r14*8+8], r11d
0x18005412b  mov     rax, [rsi+8]
0x18005412f  mov     [r15+r14*8+10h], rax
0x180054134  mov     [r15+r14*8+28h], rdi
0x180054139  mov     [r15+r14*8+20h], rdi
0x18005413e  mov     [r15+r14*8+18h], rdi
0x180054143  mov     [r15+r14*8+30h], rdi
0x180054148  mov     [r15+r14*8+48h], edi
0x18005414d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180054154  mov     [r15+r14*8+4Ch], edi
0x180054159  movdqu  xmmword ptr [r15+r14*8+38h], xmm0
0x180054160  mov     r14d, [rsp+78h+arg_8]
0x180054168  add     r14d, ebp
0x18005416b  mov     [rsp+78h+arg_8], r14d
0x180054173  add     r12d, ebp
0x180054176  cmp     [rsi], edi
0x180054178  jnz     short loc_180054182
0x18005417a  mov     rsi, rdi
0x18005417d  jmp     loc_180054015
0x180054182  mov     eax, [rsi]
0x180054184  add     rsi, rax
0x180054187  jmp     loc_180054015
0x18005418c  mov     ebp, 80030008h
0x180054191  jmp     short loc_1800541A1
0x180054193  cmp     r12d, [r13+0]
0x180054197  mov     ebp, edi
0x180054199  mov     [r13+0], r12d
0x18005419d  setnz   bpl
0x1800541a1  mov     rbx, [rsp+78h+arg_0]
0x1800541a9  mov     rcx, [rbx+8]
0x1800541ad  mov     rdx, [rcx]
0x1800541b0  mov     rax, [rdx+20h]
0x1800541b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541b9  mov     rbx, [rsp+78h+arg_10]
0x1800541c1  mov     eax, ebp
0x1800541c3  add     rsp, 40h
0x1800541c7  pop     r15
0x1800541c9  pop     r14
0x1800541cb  pop     r13
0x1800541cd  pop     r12
0x1800541cf  pop     rdi
0x1800541d0  pop     rsi
0x1800541d1  pop     rbp
0x1800541d2  retn
```
