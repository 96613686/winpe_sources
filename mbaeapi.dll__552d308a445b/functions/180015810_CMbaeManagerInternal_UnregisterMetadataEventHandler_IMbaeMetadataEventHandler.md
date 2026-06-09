# CMbaeManagerInternal::UnregisterMetadataEventHandler(IMbaeMetadataEventHandler *)

- ea: `0x180015810`
- end: `0x18001594f`
- name: `?UnregisterMetadataEventHandler@CMbaeManagerInternal@@UEAAJPEAUIMbaeMetadataEventHandler@@@Z`
- size: `319`
- prototype: `__int64 __fastcall(CMbaeManagerInternal *__hidden this, struct IMbaeMetadataEventHandler *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000ec4c`
- `0x180014410`
- `0x180015810`
- `0x18005c010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180015903`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180015903`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015834`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015834`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015887`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015887`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180015875`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180015875`

## pseudocode

```c
__int64 __fastcall CMbaeManagerInternal::UnregisterMetadataEventHandler(
        RTL_SRWLOCK *this,
        struct IMbaeMetadataEventHandler *a2)
{
  int Ptr; // edx
  struct IMbaeMetadataEventHandler **v6; // r8
  int v7; // ecx
  int v8; // esi
  unsigned int v9; // edi
  PVOID v10; // rcx
  __int64 v11; // rcx
  errno_t v12; // eax

  if ( !a2 )
    return 2147942487LL;
  AcquireSRWLockExclusive(this + 10);
  Ptr = (int)this[12].Ptr;
  if ( Ptr <= 0 )
    goto LABEL_7;
  v6 = (struct IMbaeMetadataEventHandler **)this[11].Ptr;
  v7 = 0;
  while ( v6[v7] != a2 )
  {
    if ( ++v7 >= Ptr )
      goto LABEL_7;
  }
  if ( v7 < 0 || v7 >= Ptr )
  {
LABEL_7:
    v8 = 0;
  }
  else
  {
    if ( v7 != Ptr - 1 )
    {
      v12 = memmove_s(&v6[v7], 8LL * (Ptr - v7), &v6[v7 + 1], 8LL * (Ptr - v7 - 1));
      if ( v12 )
      {
        if ( v12 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v12 == 22 || v12 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v12 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
    }
    --LODWORD(this[12].Ptr);
    v8 = 1;
  }
  v9 = v8 == 0 ? 0x80070490 : 0;
  if ( !LODWORD(this[12].Ptr) )
  {
    v10 = this[9].Ptr;
    if ( v10 )
    {
      EvtClose(v10);
      this[9].Ptr = 0;
    }
  }
  ReleaseSRWLockExclusive(this + 10);
  if ( (_BYTE)v8 )
    (*(void (__fastcall **)(struct IMbaeMetadataEventHandler *))(*(_QWORD *)a2 + 16LL))(a2);
  if ( (CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits & 1) != 0 )
    McTemplateU0sd_EventWriteTransfer(
      v11,
      CMbaeManagerInternal_cpp439,
      "CMbaeManagerInternal::UnregisterMetadataEventHandler",
      v9);
  return v9;
}

```

## disassembly

```asm
0x180015810  push    rbx
0x180015812  push    rbp
0x180015813  push    rsi
0x180015814  push    rdi
0x180015815  push    r14
0x180015817  sub     rsp, 20h
0x18001581b  mov     r14, rdx
0x18001581e  mov     rbx, rcx
0x180015821  test    rdx, rdx
0x180015824  jnz     short loc_180015830
0x180015826  mov     eax, 80070057h
0x18001582b  jmp     loc_1800158C2
0x180015830  add     rcx, 50h ; 'P'; SRWLock
0x180015834  call    cs:__imp_AcquireSRWLockExclusive
0x18001583a  mov     edx, [rbx+60h]
0x18001583d  test    edx, edx
0x18001583f  jle     short loc_180015856
0x180015841  mov     r8, [rbx+58h]
0x180015845  xor     ecx, ecx
0x180015847  movsxd  rax, ecx
0x18001584a  cmp     [r8+rax*8], r14
0x18001584e  jz      short loc_1800158CD
0x180015850  inc     ecx
0x180015852  cmp     ecx, edx
0x180015854  jl      short loc_180015847
0x180015856  xor     esi, esi
0x180015858  mov     eax, esi
0x18001585a  neg     eax
0x18001585c  sbb     edi, edi
0x18001585e  not     edi
0x180015860  and     edi, 80070490h
0x180015866  cmp     dword ptr [rbx+60h], 0
0x18001586a  jnz     short loc_180015883
0x18001586c  mov     rcx, [rbx+48h]; Object
0x180015870  test    rcx, rcx
0x180015873  jz      short loc_180015883
0x180015875  call    cs:__imp_EvtClose
0x18001587b  mov     qword ptr [rbx+48h], 0
0x180015883  lea     rcx, [rbx+50h]; SRWLock
0x180015887  call    cs:__imp_ReleaseSRWLockExclusive
0x18001588d  test    sil, sil
0x180015890  jz      short loc_1800158A1
0x180015892  mov     rax, [r14]
0x180015895  mov     rcx, r14
0x180015898  mov     rax, [rax+10h]
0x18001589c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158a1  test    cs:CtlGuid_9648eb920a0d3880c87e6d64dd1565d1EnableBits, 1
0x1800158a8  jz      short loc_1800158C0
0x1800158aa  mov     r9d, edi
0x1800158ad  lea     r8, aCmbaemanagerin_2; "CMbaeManagerInternal::UnregisterMetadat"...
0x1800158b4  lea     rdx, CMbaeManagerInternal_cpp439
0x1800158bb  call    McTemplateU0sd_EventWriteTransfer
0x1800158c0  mov     eax, edi
0x1800158c2  add     rsp, 20h
0x1800158c6  pop     r14
0x1800158c8  pop     rdi
0x1800158c9  pop     rsi
0x1800158ca  pop     rbp
0x1800158cb  pop     rbx
0x1800158cc  retn
0x1800158cd  cmp     ecx, 0FFFFFFFFh
0x1800158d0  jz      short loc_180015856
0x1800158d2  test    ecx, ecx
0x1800158d4  js      short loc_180015856
0x1800158d6  cmp     ecx, edx
0x1800158d8  jge     loc_180015856
0x1800158de  lea     eax, [rdx-1]
0x1800158e1  cmp     ecx, eax
0x1800158e3  jz      short loc_180015921
0x1800158e5  sub     edx, ecx
0x1800158e7  movsxd  rcx, ecx
0x1800158ea  lea     eax, [rdx-1]
0x1800158ed  movsxd  rdx, edx
0x1800158f0  movsxd  r9, eax
0x1800158f3  lea     rcx, [r8+rcx*8]; Destination
0x1800158f7  shl     r9, 3; SourceSize
0x1800158fb  lea     r8, [rcx+8]; Source
0x1800158ff  shl     rdx, 3; DestinationSize
0x180015903  call    cs:__imp_memmove_s
0x180015909  test    eax, eax
0x18001590b  jz      short loc_180015921
0x18001590d  cmp     eax, 0Ch
0x180015910  jz      short loc_180015944
0x180015912  cmp     eax, 16h
0x180015915  jz      short loc_180015939
0x180015917  cmp     eax, 22h ; '"'
0x18001591a  jz      short loc_180015939
0x18001591c  cmp     eax, 50h ; 'P'
0x18001591f  jnz     short loc_18001592E
0x180015921  dec     dword ptr [rbx+60h]
0x180015924  mov     esi, 1
0x180015929  jmp     loc_180015858
0x18001592e  mov     ecx, 80004005h; int
0x180015933  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015939  mov     ecx, 80070057h; int
0x18001593e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015944  mov     ecx, 8007000Eh; int
0x180015949  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
