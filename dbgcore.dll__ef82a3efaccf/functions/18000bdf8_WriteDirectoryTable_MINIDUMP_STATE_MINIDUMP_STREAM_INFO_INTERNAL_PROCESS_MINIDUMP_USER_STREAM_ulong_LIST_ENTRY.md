# WriteDirectoryTable(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *,_MINIDUMP_USER_STREAM *,ulong,_LIST_ENTRY *)

- ea: `0x18000bdf8`
- end: `0x18000c193`
- name: `?WriteDirectoryTable@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@PEAU_MINIDUMP_USER_STREAM@@KPEAU_LIST_ENTRY@@@Z`
- size: `923`
- prototype: `__int64 __usercall@<rax>(struct _MINIDUMP_STATE *@<rcx>, struct _MINIDUMP_STREAM_INFO *@<rdx>, struct _INTERNAL_PROCESS *@<r8>, struct _MINIDUMP_USER_STREAM *@<r9>, unsigned int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x18000bd54`
- `0x18000bdf8`
- `0x18002c010`

## string_xrefs

- `0x18000be36`: `WriteDirectoryTable.Seek(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteDirectoryTable(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3,
        struct _MINIDUMP_USER_STREAM *a4,
        unsigned int a5,
        struct _LIST_ENTRY *a6)
{
  int v10; // eax
  unsigned int v11; // ebp
  __int64 result; // rax
  unsigned int v13; // edx
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // esi
  unsigned int v25; // ebx
  __int64 v26; // r14
  struct _LIST_ENTRY *Flink; // rbx
  struct _LIST_ENTRY *v28; // r12
  struct _LIST_ENTRY *v29; // rcx
  unsigned int v30; // ebp
  __int64 v31; // r15

  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 3) + 24LL))(
          *((_QWORD *)a1 + 3),
          0,
          *((unsigned int *)a2 + 3),
          0);
  v11 = v10;
  if ( v10 )
  {
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
      *((_QWORD *)a1 + 5),
      4,
      "WriteDirectoryTable.Seek(0x%x) failed, 0x%08x",
      *((unsigned int *)a2 + 3),
      v10);
    return v11;
  }
  else
  {
    v13 = 8;
    if ( *((_DWORD *)a2 + 14) != 64 )
      v13 = 3;
    result = WriteDirectoryEntry(a1, v13, *((_DWORD *)a2 + 11), *((unsigned int *)a2 + 12));
    if ( !(_DWORD)result )
    {
      if ( !*((_DWORD *)a3 + 20)
        || (result = WriteDirectoryEntry(a1, 0x11u, *((_DWORD *)a2 + 15), *((unsigned int *)a2 + 16)), !(_DWORD)result) )
      {
        result = WriteDirectoryEntry(a1, 4u, *((_DWORD *)a2 + 18), *((unsigned int *)a2 + 19));
        if ( !(_DWORD)result )
        {
          if ( *((struct _INTERNAL_PROCESS **)a3 + 17) == (struct _INTERNAL_PROCESS *)((char *)a3 + 136)
            || (result = WriteDirectoryEntry(a1, 0xEu, *((_DWORD *)a2 + 21), *((unsigned int *)a2 + 22)), !(_DWORD)result) )
          {
            if ( *((struct _INTERNAL_PROCESS **)a3 + 19) == (struct _INTERNAL_PROCESS *)((char *)a3 + 152)
              || (result = WriteDirectoryEntry(a1, 0xDu, *((_DWORD *)a2 + 24), *((unsigned int *)a2 + 25)),
                  !(_DWORD)result) )
            {
              v14 = *((_DWORD *)a2 + 49);
              if ( !v14 || (result = WriteDirectoryEntry(a1, 0x13u, *((_DWORD *)a2 + 48), v14), !(_DWORD)result) )
              {
                v15 = *((_DWORD *)a1 + 14);
                v16 = (v15 & 0x4000000) != 0 ? 25 : (v15 & 2) != 0 ? 9 : 5;
                result = WriteDirectoryEntry(a1, v16, *((_DWORD *)a2 + 26), *((unsigned int *)a2 + 27));
                if ( !(_DWORD)result )
                {
                  v17 = *((_DWORD *)a2 + 43);
                  if ( !v17 || (result = WriteDirectoryEntry(a1, 0x10u, *((_DWORD *)a2 + 42), v17), !(_DWORD)result) )
                  {
                    result = WriteDirectoryEntry(a1, 6u, *((_DWORD *)a2 + 9), *((unsigned int *)a2 + 10));
                    if ( !(_DWORD)result )
                    {
                      result = WriteDirectoryEntry(a1, 7u, *((_DWORD *)a2 + 5), *((unsigned int *)a2 + 6));
                      if ( !(_DWORD)result )
                      {
                        result = WriteDirectoryEntry(a1, 0xFu, *((_DWORD *)a2 + 8), 0x554u);
                        if ( !(_DWORD)result )
                        {
                          v18 = *((_DWORD *)a2 + 45);
                          if ( !v18
                            || (result = WriteDirectoryEntry(a1, 0xCu, *((_DWORD *)a2 + 44), v18), !(_DWORD)result) )
                          {
                            v19 = *((_DWORD *)a2 + 47);
                            if ( !v19
                              || (result = WriteDirectoryEntry(a1, 0x12u, *((_DWORD *)a2 + 46), v19), !(_DWORD)result) )
                            {
                              v20 = *((_DWORD *)a2 + 52);
                              if ( !v20
                                || (result = WriteDirectoryEntry(a1, 0x15u, *((_DWORD *)a2 + 51), v20), !(_DWORD)result) )
                              {
                                v21 = *((_DWORD *)a2 + 54);
                                if ( !v21
                                  || (result = WriteDirectoryEntry(a1, 0x16u, *((_DWORD *)a2 + 53), v21), !(_DWORD)result) )
                                {
                                  v22 = *((_DWORD *)a2 + 56);
                                  if ( !v22
                                    || (result = WriteDirectoryEntry(a1, 0x17u, *((_DWORD *)a2 + 55), v22),
                                        !(_DWORD)result) )
                                  {
                                    v23 = *((_DWORD *)a2 + 58);
                                    if ( !v23
                                      || (result = WriteDirectoryEntry(a1, 0x18u, *((_DWORD *)a2 + 57), v23),
                                          !(_DWORD)result) )
                                    {
                                      v24 = *((_DWORD *)a2 + 38);
                                      v25 = 0;
                                      if ( a5 )
                                      {
                                        while ( 1 )
                                        {
                                          v26 = v25;
                                          result = WriteDirectoryEntry(a1, a4[v26].Type, v24, a4[v26].BufferSize);
                                          if ( (_DWORD)result )
                                            break;
                                          v24 += a4[v26].BufferSize;
                                          if ( ++v25 >= a5 )
                                            goto LABEL_38;
                                        }
                                      }
                                      else
                                      {
LABEL_38:
                                        Flink = a6->Flink;
                                        do
                                        {
LABEL_44:
                                          if ( Flink == a6 )
                                            return 0;
                                          v28 = Flink - 1;
                                          Flink = Flink->Flink;
                                          v29 = v28->Flink;
                                        }
                                        while ( !v28->Flink->Flink );
                                        v30 = 0;
                                        while ( 1 )
                                        {
                                          v31 = v30;
                                          result = WriteDirectoryEntry(
                                                     a1,
                                                     (unsigned int)(*(struct _LIST_ENTRY **)((char *)&v29->Flink + 4))[v31].Flink,
                                                     v24,
                                                     HIDWORD((*(struct _LIST_ENTRY **)((char *)&v29->Flink + 4))[v31].Flink));
                                          if ( (_DWORD)result )
                                            break;
                                          v29 = v28->Flink;
                                          ++v30;
                                          v24 += HIDWORD((*(struct _LIST_ENTRY **)((char *)&v28->Flink->Flink + 4))[v31].Flink);
                                          if ( (struct _LIST_ENTRY *)v30 >= v28->Flink->Flink )
                                            goto LABEL_44;
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bdf8  push    rbx
0x18000bdfa  push    rbp
0x18000bdfb  push    rsi
0x18000bdfc  push    rdi
0x18000bdfd  push    r12
0x18000bdff  push    r14
0x18000be01  push    r15
0x18000be03  sub     rsp, 30h
0x18000be07  mov     rdi, rcx
0x18000be0a  mov     rsi, r8
0x18000be0d  mov     rcx, [rcx+18h]
0x18000be11  mov     r15, r9
0x18000be14  mov     r8d, [rdx+0Ch]
0x18000be18  mov     rbx, rdx
0x18000be1b  xor     r9d, r9d
0x18000be1e  xor     edx, edx
0x18000be20  mov     rax, [rcx]
0x18000be23  mov     rax, [rax+18h]
0x18000be27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be2c  mov     ebp, eax
0x18000be2e  test    eax, eax
0x18000be30  jz      short loc_18000BE5D
0x18000be32  mov     rcx, [rdi+28h]
0x18000be36  lea     r8, aWritedirectory; "WriteDirectoryTable.Seek(0x%x) failed, "...
0x18000be3d  mov     r9d, [rbx+0Ch]
0x18000be41  mov     [rsp+68h+var_48], ebp
0x18000be45  mov     rdx, [rcx]
0x18000be48  mov     rax, [rdx+8]
0x18000be4c  mov     edx, 4
0x18000be51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be56  mov     eax, ebp
0x18000be58  jmp     loc_18000C184
0x18000be5d  cmp     dword ptr [rbx+38h], 40h ; '@'
0x18000be61  mov     edx, 8
0x18000be66  mov     r9d, [rbx+30h]; unsigned __int64
0x18000be6a  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000be6d  mov     r8d, [rbx+2Ch]; unsigned int
0x18000be71  lea     eax, [rdx-5]
0x18000be74  cmovnz  edx, eax; unsigned int
0x18000be77  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000be7c  test    eax, eax
0x18000be7e  jnz     loc_18000C184
0x18000be84  cmp     [rsi+50h], eax
0x18000be87  jz      short loc_18000BEA4
0x18000be89  mov     r9d, [rbx+40h]; unsigned __int64
0x18000be8d  lea     edx, [rax+11h]; unsigned int
0x18000be90  mov     r8d, [rbx+3Ch]; unsigned int
0x18000be94  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000be97  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000be9c  test    eax, eax
0x18000be9e  jnz     loc_18000C184
0x18000bea4  mov     r9d, [rbx+4Ch]; unsigned __int64
0x18000bea8  mov     edx, 4; unsigned int
0x18000bead  mov     r8d, [rbx+48h]; unsigned int
0x18000beb1  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000beb4  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000beb9  test    eax, eax
0x18000bebb  jnz     loc_18000C184
0x18000bec1  lea     rax, [rsi+88h]
0x18000bec8  cmp     [rax], rax
0x18000becb  jz      short loc_18000BEEA
0x18000becd  mov     r9d, [rbx+58h]; unsigned __int64
0x18000bed1  mov     edx, 0Eh; unsigned int
0x18000bed6  mov     r8d, [rbx+54h]; unsigned int
0x18000beda  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bedd  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bee2  test    eax, eax
0x18000bee4  jnz     loc_18000C184
0x18000beea  lea     rax, [rsi+98h]
0x18000bef1  cmp     [rax], rax
0x18000bef4  jz      short loc_18000BF13
0x18000bef6  mov     r9d, [rbx+64h]; unsigned __int64
0x18000befa  mov     edx, 0Dh; unsigned int
0x18000beff  mov     r8d, [rbx+60h]; unsigned int
0x18000bf03  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bf06  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bf0b  test    eax, eax
0x18000bf0d  jnz     loc_18000C184
0x18000bf13  mov     eax, [rbx+0C4h]
0x18000bf19  test    eax, eax
0x18000bf1b  jz      short loc_18000BF3C
0x18000bf1d  mov     r8d, [rbx+0C0h]; unsigned int
0x18000bf24  mov     r9d, eax; unsigned __int64
0x18000bf27  mov     edx, 13h; unsigned int
0x18000bf2c  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bf2f  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bf34  test    eax, eax
0x18000bf36  jnz     loc_18000C184
0x18000bf3c  mov     eax, [rdi+38h]
0x18000bf3f  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bf42  mov     r8d, [rbx+68h]; unsigned int
0x18000bf46  mov     r9d, [rbx+6Ch]; unsigned __int64
0x18000bf4a  bt      eax, 1Ah
0x18000bf4e  jnb     loc_18000C124
0x18000bf54  mov     edx, 19h; unsigned int
0x18000bf59  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bf5e  test    eax, eax
0x18000bf60  jnz     loc_18000C184
0x18000bf66  mov     eax, [rbx+0ACh]
0x18000bf6c  test    eax, eax
0x18000bf6e  jz      short loc_18000BF8F
0x18000bf70  mov     r8d, [rbx+0A8h]; unsigned int
0x18000bf77  mov     r9d, eax; unsigned __int64
0x18000bf7a  mov     edx, 10h; unsigned int
0x18000bf7f  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bf82  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bf87  test    eax, eax
0x18000bf89  jnz     loc_18000C184
0x18000bf8f  mov     r9d, [rbx+28h]; unsigned __int64
0x18000bf93  mov     edx, 6; unsigned int
0x18000bf98  mov     r8d, [rbx+24h]; unsigned int
0x18000bf9c  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bf9f  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bfa4  test    eax, eax
0x18000bfa6  jnz     loc_18000C184
0x18000bfac  mov     r9d, [rbx+18h]; unsigned __int64
0x18000bfb0  lea     edx, [rax+7]; unsigned int
0x18000bfb3  mov     r8d, [rbx+14h]; unsigned int
0x18000bfb7  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bfba  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bfbf  test    eax, eax
0x18000bfc1  jnz     loc_18000C184
0x18000bfc7  mov     r8d, [rbx+20h]; unsigned int
0x18000bfcb  lea     edx, [rax+0Fh]; unsigned int
0x18000bfce  mov     r9d, 554h; unsigned __int64
0x18000bfd4  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000bfd7  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000bfdc  test    eax, eax
0x18000bfde  jnz     loc_18000C184
0x18000bfe4  mov     eax, [rbx+0B4h]
0x18000bfea  test    eax, eax
0x18000bfec  jz      short loc_18000C00D
0x18000bfee  mov     r8d, [rbx+0B0h]; unsigned int
0x18000bff5  mov     r9d, eax; unsigned __int64
0x18000bff8  mov     edx, 0Ch; unsigned int
0x18000bffd  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c000  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c005  test    eax, eax
0x18000c007  jnz     loc_18000C184
0x18000c00d  mov     eax, [rbx+0BCh]
0x18000c013  test    eax, eax
0x18000c015  jz      short loc_18000C036
0x18000c017  mov     r8d, [rbx+0B8h]; unsigned int
0x18000c01e  mov     r9d, eax; unsigned __int64
0x18000c021  mov     edx, 12h; unsigned int
0x18000c026  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c029  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c02e  test    eax, eax
0x18000c030  jnz     loc_18000C184
0x18000c036  mov     eax, [rbx+0D0h]
0x18000c03c  test    eax, eax
0x18000c03e  jz      short loc_18000C05F
0x18000c040  mov     r8d, [rbx+0CCh]; unsigned int
0x18000c047  mov     r9d, eax; unsigned __int64
0x18000c04a  mov     edx, 15h; unsigned int
0x18000c04f  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c052  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c057  test    eax, eax
0x18000c059  jnz     loc_18000C184
0x18000c05f  mov     eax, [rbx+0D8h]
0x18000c065  test    eax, eax
0x18000c067  jz      short loc_18000C088
0x18000c069  mov     r8d, [rbx+0D4h]; unsigned int
0x18000c070  mov     r9d, eax; unsigned __int64
0x18000c073  mov     edx, 16h; unsigned int
0x18000c078  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c07b  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c080  test    eax, eax
0x18000c082  jnz     loc_18000C184
0x18000c088  mov     eax, [rbx+0E0h]
0x18000c08e  test    eax, eax
0x18000c090  jz      short loc_18000C0B1
0x18000c092  mov     r8d, [rbx+0DCh]; unsigned int
0x18000c099  mov     r9d, eax; unsigned __int64
0x18000c09c  mov     edx, 17h; unsigned int
0x18000c0a1  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c0a4  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c0a9  test    eax, eax
0x18000c0ab  jnz     loc_18000C184
0x18000c0b1  mov     eax, [rbx+0E8h]
0x18000c0b7  test    eax, eax
0x18000c0b9  jz      short loc_18000C0DA
0x18000c0bb  mov     r8d, [rbx+0E4h]; unsigned int
0x18000c0c2  mov     r9d, eax; unsigned __int64
0x18000c0c5  mov     edx, 18h; unsigned int
0x18000c0ca  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c0cd  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c0d2  test    eax, eax
0x18000c0d4  jnz     loc_18000C184
0x18000c0da  mov     esi, [rbx+98h]
0x18000c0e0  xor     ebx, ebx
0x18000c0e2  mov     ebp, [rsp+68h+arg_20]
0x18000c0e9  test    ebp, ebp
0x18000c0eb  jz      short loc_18000C117
0x18000c0ed  mov     r14d, ebx
0x18000c0f0  mov     r8d, esi; unsigned int
0x18000c0f3  shl     r14, 4
0x18000c0f7  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c0fa  mov     r9d, [r14+r15+4]; unsigned __int64
0x18000c0ff  mov     edx, [r14+r15]; unsigned int
0x18000c103  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c108  test    eax, eax
0x18000c10a  jnz     short loc_18000C184
0x18000c10c  add     esi, [r14+r15+4]
0x18000c111  inc     ebx
0x18000c113  cmp     ebx, ebp
0x18000c115  jb      short loc_18000C0ED
0x18000c117  mov     r14, [rsp+68h+arg_28]
0x18000c11f  mov     rbx, [r14]
0x18000c122  jmp     short loc_18000C17D
0x18000c124  and     al, 2
0x18000c126  neg     al
0x18000c128  sbb     edx, edx
0x18000c12a  and     edx, 4
0x18000c12d  add     edx, 5
0x18000c130  jmp     loc_18000BF59
0x18000c135  lea     r12, [rbx-10h]
0x18000c139  mov     rbx, [rbx]
0x18000c13c  mov     rcx, [r12]
0x18000c140  cmp     dword ptr [rcx], 0
0x18000c143  jbe     short loc_18000C17D
0x18000c145  xor     ebp, ebp
0x18000c147  mov     rdx, [rcx+4]
0x18000c14b  mov     r8d, esi; unsigned int
0x18000c14e  mov     r15d, ebp
0x18000c151  mov     rcx, rdi; struct _MINIDUMP_STATE *
0x18000c154  shl     r15, 4
0x18000c158  mov     r9d, [rdx+r15+4]; unsigned __int64
0x18000c15d  mov     edx, [rdx+r15]; unsigned int
0x18000c161  call    ?WriteDirectoryEntry@@YAJPEAU_MINIDUMP_STATE@@KK_K@Z; WriteDirectoryEntry(_MINIDUMP_STATE *,ulong,ulong,unsigned __int64)
0x18000c166  test    eax, eax
0x18000c168  jnz     short loc_18000C184
0x18000c16a  mov     rcx, [r12]
0x18000c16e  inc     ebp
0x18000c170  mov     rax, [rcx+4]
0x18000c174  add     esi, [rax+r15+4]
0x18000c179  cmp     ebp, [rcx]
0x18000c17b  jb      short loc_18000C147
0x18000c17d  cmp     rbx, r14
0x18000c180  jnz     short loc_18000C135
0x18000c182  xor     eax, eax
0x18000c184  add     rsp, 30h
0x18000c188  pop     r15
0x18000c18a  pop     r14
0x18000c18c  pop     r12
0x18000c18e  pop     rdi
0x18000c18f  pop     rsi
0x18000c190  pop     rbp
0x18000c191  pop     rbx
0x18000c192  retn
```
