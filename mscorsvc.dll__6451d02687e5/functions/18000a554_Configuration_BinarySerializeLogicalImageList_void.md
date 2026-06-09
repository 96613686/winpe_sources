# Configuration::BinarySerializeLogicalImageList(void)

- ea: `0x18000a554`
- end: `0x18000a9c9`
- name: `?BinarySerializeLogicalImageList@Configuration@@QEAAXXZ`
- size: `1141`
- prototype: `void __fastcall(Configuration *__hidden this)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180009850`
- `0x180024c50`
- `0x18002db88`

## callees

- `0x18000a3a4`
- `0x18000a48c`
- `0x18000a554`
- `0x18000b0f0`
- `0x18000c80c`
- `0x180030ab8`
- `0x180030d84`
- `0x1800310f0`
- `0x180032d74`
- `0x180035b90`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000a7f2`
- `KERNEL32!HeapFree` at `0x18000a829`
- `KERNEL32!HeapFree` at `0x18000a993`
- `KERNEL32!HeapFree` at `0x18000a7f2`
- `KERNEL32!HeapFree` at `0x18000a829`
- `KERNEL32!HeapFree` at `0x18000a993`
- `KERNEL32!GetProcessHeap` at `0x18000a7dd`
- `KERNEL32!GetProcessHeap` at `0x18000a814`
- `KERNEL32!GetProcessHeap` at `0x18000a97e`
- `KERNEL32!GetProcessHeap` at `0x18000a7dd`
- `KERNEL32!GetProcessHeap` at `0x18000a814`
- `KERNEL32!GetProcessHeap` at `0x18000a97e`

## pseudocode

```c
void __fastcall Configuration::BinarySerializeLogicalImageList(Configuration *this)
{
  unsigned int v2; // ebx
  __int64 v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  char v6; // bl
  __int64 v7; // rbx
  const unsigned __int16 *v8; // rdx
  LPVOID v9; // r10
  __int64 v10; // rax
  __int64 v11; // r10
  __int64 v12; // r10
  __int64 v13; // r10
  int v14; // edi
  int v15; // ebx
  int v16; // edi
  int v17; // ebx
  void *v18; // rdi
  HANDLE ProcessHeap; // rax
  void *v20; // rdi
  HANDLE v21; // rax
  Configuration *v22; // rcx
  __int64 v23; // rbx
  Configuration *v24; // rcx
  const unsigned __int16 **v25; // r8
  void *v26; // rbx
  HANDLE v27; // rax
  int v28; // [rsp+28h] [rbp-E0h] BYREF
  __int64 Src; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v30; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C8h]
  LPVOID v32; // [rsp+48h] [rbp-C0h]
  __int64 v33; // [rsp+50h] [rbp-B8h] BYREF
  int v34; // [rsp+58h] [rbp-B0h]
  __int128 v35; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+78h] [rbp-90h] BYREF
  int v37; // [rsp+88h] [rbp-80h] BYREF
  __int64 v38; // [rsp+8Ch] [rbp-7Ch]
  LPVOID v39; // [rsp+98h] [rbp-70h]
  __int16 v40; // [rsp+A0h] [rbp-68h] BYREF
  int v41; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v42; // [rsp+1ACh] [rbp+A4h]
  LPVOID lpMem; // [rsp+1B8h] [rbp+B0h]
  __int16 v44; // [rsp+1C0h] [rbp+B8h] BYREF

  if ( *((_DWORD *)this + 161) )
  {
    v30 = 0;
    LODWORD(v31) = 0;
    v32 = 0;
    LODWORD(Src) = *((_DWORD *)this + 8) >> 3;
    v2 = Src;
    WriteBuffer::Write((WriteBuffer *)&v30, &Src, 4u);
    if ( v2 )
    {
      v3 = 0;
      v4 = v2;
      do
      {
        v5 = *(_QWORD *)(v3 + *((_QWORD *)this + 6));
        v6 = 0;
        if ( *(_QWORD *)(v5 + 72) )
        {
          v38 = 256;
          v39 = &v40;
          v37 = 2;
          v40 = 0;
          v7 = *(_QWORD *)(v5 + 72);
          if ( v7 )
          {
            SString::ConvertToUnicode(*(SString **)(v5 + 72));
            v8 = *(const unsigned __int16 **)(v7 + 16);
          }
          else
          {
            v8 = 0;
          }
          v42 = 512;
          lpMem = &v44;
          v41 = 2;
          v44 = 0;
          SString::Set((SString *)&v41, v8);
          if ( (unsigned int)SString::IsRepresentation(&v41, 7) )
          {
            v9 = lpMem;
          }
          else
          {
            SString::ConvertToANSI((SString *)&v41, (struct SString *)&v37);
            v9 = v39;
          }
          v10 = -1;
          do
            ++v10;
          while ( *((_BYTE *)v9 + v10) );
          if ( v10 == 38
            && *(_BYTE *)v9 == 123
            && *((_BYTE *)v9 + 9) == 45
            && *((_BYTE *)v9 + 14) == 45
            && *((_BYTE *)v9 + 19) == 45
            && *((_BYTE *)v9 + 24) == 45
            && *((_BYTE *)v9 + 37) == 125
            && (int)GetHex((const char *)v9 + 1, 4, &v36) >= 0
            && (int)GetHex((const char *)(v11 + 10), 2, (char *)&v36 + 4) >= 0
            && (int)GetHex((const char *)(v12 + 15), 2, (char *)&v36 + 6) >= 0 )
          {
            v14 = 0;
            v15 = 0;
            while ( (int)GetHex((const char *)(v13 + v15 + 20LL), 1, (char *)&v36 + v14 + 8) >= 0 )
            {
              ++v14;
              v15 += 2;
              if ( v15 >= 4 )
              {
                v16 = 0;
                v17 = 0;
                while ( (int)GetHex((const char *)(v13 + v17 + 25LL), 1, (char *)&v36 + v16 + 10) >= 0 )
                {
                  ++v16;
                  v17 += 2;
                  if ( v17 >= 12 )
                  {
                    v6 = 1;
                    goto LABEL_31;
                  }
                }
                break;
              }
            }
          }
          v6 = 0;
LABEL_31:
          if ( (v42 & 0x800000000LL) != 0 )
          {
            v18 = lpMem;
            if ( lpMem )
            {
              ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                ProcessHeap = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
              }
              HeapFree(ProcessHeap, 0, v18);
            }
          }
          if ( (v38 & 0x800000000LL) != 0 )
          {
            v20 = v39;
            if ( v39 )
            {
              v21 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
              if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
              {
                v21 = GetProcessHeap();
                `ClrFreeInProcessHeap'::`2'::ProcessHeap = v21;
              }
              HeapFree(v21, 0, v20);
            }
          }
        }
        LOBYTE(v28) = v6;
        WriteBuffer::Write((WriteBuffer *)&v30, &v28, 1u);
        if ( v6 )
        {
          v35 = v36;
          WriteBuffer::Write((WriteBuffer *)&v30, &v35, 0x10u);
        }
        LODWORD(Src) = *(_DWORD *)(v5 + 16);
        WriteBuffer::Write((WriteBuffer *)&v30, &Src, 4u);
        Configuration::BinarySerializeImage(v22, (struct WriteBuffer *)&v30, *(const unsigned __int16 ***)(v5 + 88));
        v23 = *(_QWORD *)(v5 + 104);
        LOBYTE(v28) = v23 != 0;
        WriteBuffer::Write((WriteBuffer *)&v30, &v28, 1u);
        if ( v23 )
        {
          v25 = *(const unsigned __int16 ***)(v5 + 104);
          if ( !v25 )
            v25 = *(const unsigned __int16 ***)(v5 + 88);
          Configuration::BinarySerializeImage(v24, (struct WriteBuffer *)&v30, v25);
        }
        Configuration::BinarySerializeDependencyList((__int64)this, (WriteBuffer *)&v30, v5 + 48);
        Configuration::BinarySerializeDependencyList((__int64)this, (WriteBuffer *)&v30, v5 + 24);
        v3 += 8;
        --v4;
      }
      while ( v4 );
    }
    v33 = 0;
    v34 = 0;
    Node::GetRegKeyThrowing(this, &v33);
    (*(void (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v33 + 56LL))(v33, L"ImageList", &v30);
    if ( v34 )
    {
      if ( v33 )
        (**(void (__fastcall ***)(__int64, __int64))v33)(v33, 1);
      v34 = 0;
    }
    if ( (v31 & 8) != 0 )
    {
      v26 = v32;
      if ( v32 )
      {
        v27 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v27 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v27;
        }
        HeapFree(v27, 0, v26);
      }
    }
  }
}

```

## disassembly

```asm
0x18000a554  mov     rax, rsp
0x18000a557  mov     [rax+10h], rbx
0x18000a55b  mov     [rax+18h], rsi
0x18000a55f  mov     [rax+20h], rdi
0x18000a563  push    rbp
0x18000a564  push    r12
0x18000a566  push    r13
0x18000a568  push    r14
0x18000a56a  push    r15
0x18000a56c  lea     rbp, [rax-2F8h]
0x18000a573  sub     rsp, 3D0h
0x18000a57a  mov     rax, cs:__security_cookie
0x18000a581  xor     rax, rsp
0x18000a584  mov     [rbp+2F0h+var_30], rax
0x18000a58b  mov     rsi, rcx
0x18000a58e  xor     r13d, r13d
0x18000a591  cmp     [rcx+284h], r13d
0x18000a598  jz      loc_18000A999
0x18000a59e  mov     [rsp+3F0h+var_3C0], r13
0x18000a5a3  mov     dword ptr [rsp+3F0h+var_3B8], r13d
0x18000a5a8  mov     [rsp+3F0h+var_3B0], r13
0x18000a5ad  mov     ebx, [rcx+20h]
0x18000a5b0  shr     ebx, 3
0x18000a5b3  mov     dword ptr [rsp+3F0h+Src], ebx
0x18000a5b7  lea     r8d, [r13+4]; unsigned int
0x18000a5bb  lea     rdx, [rsp+3F0h+Src]; Src
0x18000a5c0  lea     rcx, [rsp+3F0h+var_3C0]; this
0x18000a5c5  call    ?Write@WriteBuffer@@QEAAXPEAXI@Z; WriteBuffer::Write(void *,uint)
0x18000a5ca  test    ebx, ebx
0x18000a5cc  jz      loc_18000A904
0x18000a5d2  mov     r15d, r13d
0x18000a5d5  mov     r12d, ebx
0x18000a5d8  mov     rax, [rsi+30h]
0x18000a5dc  mov     r14, [r15+rax]
0x18000a5e0  mov     bl, r13b
0x18000a5e3  cmp     [r14+48h], r13
0x18000a5e7  jz      loc_18000A82F
0x18000a5ed  mov     [rbp+2F0h+var_370], r13
0x18000a5f1  mov     [rbp+2F0h+var_370+4], 100h
0x18000a5f9  mov     [rbp+2F0h+var_360], r13
0x18000a5fd  lea     rax, [rbp+2F0h+var_358]
0x18000a601  mov     [rbp+2F0h+var_360], rax
0x18000a605  mov     dword ptr [rbp+2F0h+var_370], 2
0x18000a60c  mov     rax, [rbp+2F0h+var_360]
0x18000a610  mov     [rax], r13w
0x18000a614  mov     rbx, [r14+48h]
0x18000a618  test    rbx, rbx
0x18000a61b  jnz     short loc_18000A622
0x18000a61d  mov     rdx, r13
0x18000a620  jmp     short loc_18000A62E
0x18000a622  mov     rcx, rbx; this
0x18000a625  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000a62a  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18000a62e  mov     [rbp+2F0h+var_250], r13
0x18000a635  mov     [rbp+2F0h+var_250+4], 200h
0x18000a640  mov     [rbp+2F0h+lpMem], r13
0x18000a647  lea     rax, [rbp+2F0h+var_238]
0x18000a64e  mov     [rbp+2F0h+lpMem], rax
0x18000a655  mov     dword ptr [rbp+2F0h+var_250], 2
0x18000a65f  mov     rax, [rbp+2F0h+lpMem]
0x18000a666  mov     [rax], r13w
0x18000a66a  lea     rcx, [rbp+2F0h+var_250]; this
0x18000a671  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18000a676  nop
0x18000a677  mov     edx, 7
0x18000a67c  lea     rcx, [rbp+2F0h+var_250]
0x18000a683  call    ?IsRepresentation@SString@@AEBAHW4Representation@1@@Z; SString::IsRepresentation(SString::Representation)
0x18000a688  test    eax, eax
0x18000a68a  jz      short loc_18000A695
0x18000a68c  mov     r10, [rbp+2F0h+lpMem]
0x18000a693  jmp     short loc_18000A6A9
0x18000a695  lea     rdx, [rbp+2F0h+var_370]; struct SString *
0x18000a699  lea     rcx, [rbp+2F0h+var_250]; this
0x18000a6a0  call    ?ConvertToANSI@SString@@QEBAXAEAV1@@Z; SString::ConvertToANSI(SString &)
0x18000a6a5  mov     r10, [rbp+2F0h+var_360]
0x18000a6a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a6ad  inc     rax
0x18000a6b0  cmp     [r10+rax], r13b
0x18000a6b4  jnz     short loc_18000A6AD
0x18000a6b6  cmp     rax, 26h ; '&'
0x18000a6ba  jnz     loc_18000A7B9
0x18000a6c0  cmp     byte ptr [r10], 7Bh ; '{'
0x18000a6c4  jnz     loc_18000A7B9
0x18000a6ca  cmp     byte ptr [r10+9], 2Dh ; '-'
0x18000a6cf  jnz     loc_18000A7B9
0x18000a6d5  cmp     byte ptr [r10+0Eh], 2Dh ; '-'
0x18000a6da  jnz     loc_18000A7B9
0x18000a6e0  cmp     byte ptr [r10+13h], 2Dh ; '-'
0x18000a6e5  jnz     loc_18000A7B9
0x18000a6eb  cmp     byte ptr [r10+18h], 2Dh ; '-'
0x18000a6f0  jnz     loc_18000A7B9
0x18000a6f6  cmp     byte ptr [r10+25h], 7Dh ; '}'
0x18000a6fb  jnz     loc_18000A7B9
0x18000a701  lea     rcx, [r10+1]; char *
0x18000a705  lea     r8, [rsp+3F0h+var_388+8]; void *
0x18000a70a  lea     edx, [rax-22h]; int
0x18000a70d  call    ?GetHex@@YAJPEBDHPEAX@Z; GetHex(char const *,int,void *)
0x18000a712  test    eax, eax
0x18000a714  js      loc_18000A7B9
0x18000a71a  lea     rcx, [r10+0Ah]; char *
0x18000a71e  lea     r8, [rsp+3F0h+var_388+0Ch]; void *
0x18000a723  mov     edx, 2; int
0x18000a728  call    ?GetHex@@YAJPEBDHPEAX@Z; GetHex(char const *,int,void *)
0x18000a72d  test    eax, eax
0x18000a72f  js      loc_18000A7B9
0x18000a735  lea     rcx, [r10+0Fh]; char *
0x18000a739  lea     r8, [rsp+3F0h+var_388+0Eh]; void *
0x18000a73e  mov     edx, 2; int
0x18000a743  call    ?GetHex@@YAJPEBDHPEAX@Z; GetHex(char const *,int,void *)
0x18000a748  test    eax, eax
0x18000a74a  js      short loc_18000A7B9
0x18000a74c  mov     edi, r13d
0x18000a74f  mov     ebx, r13d
0x18000a752  movsxd  rax, edi
0x18000a755  lea     r8, [rsp+3F0h+var_378]
0x18000a75a  add     r8, rax; void *
0x18000a75d  movsxd  rcx, ebx
0x18000a760  add     rcx, 14h
0x18000a764  add     rcx, r10; char *
0x18000a767  mov     edx, 1; int
0x18000a76c  call    ?GetHex@@YAJPEBDHPEAX@Z; GetHex(char const *,int,void *)
0x18000a771  test    eax, eax
0x18000a773  js      short loc_18000A7B9
0x18000a775  inc     edi
0x18000a777  add     ebx, 2
0x18000a77a  cmp     ebx, 4
0x18000a77d  jl      short loc_18000A752
0x18000a77f  mov     edi, r13d
0x18000a782  mov     ebx, r13d
0x18000a785  lea     eax, [rdi+2]
0x18000a788  movsxd  rcx, eax
0x18000a78b  lea     r8, [rsp+3F0h+var_378]
0x18000a790  add     r8, rcx; void *
0x18000a793  movsxd  rcx, ebx
0x18000a796  add     rcx, 19h
0x18000a79a  add     rcx, r10; char *
0x18000a79d  mov     edx, 1; int
0x18000a7a2  call    ?GetHex@@YAJPEBDHPEAX@Z; GetHex(char const *,int,void *)
0x18000a7a7  test    eax, eax
0x18000a7a9  js      short loc_18000A7B9
0x18000a7ab  inc     edi
0x18000a7ad  add     ebx, 2
0x18000a7b0  cmp     ebx, 0Ch
0x18000a7b3  jl      short loc_18000A785
0x18000a7b5  mov     bl, 1
0x18000a7b7  jmp     short loc_18000A7BC
0x18000a7b9  mov     bl, r13b
0x18000a7bc  test    [rbp+2F0h+var_248], 8
0x18000a7c3  jz      short loc_18000A7F9
0x18000a7c5  mov     rdi, [rbp+2F0h+lpMem]
0x18000a7cc  test    rdi, rdi
0x18000a7cf  jz      short loc_18000A7F9
0x18000a7d1  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000a7d8  test    rax, rax
0x18000a7db  jnz     short loc_18000A7EA
0x18000a7dd  call    cs:__imp_GetProcessHeap
0x18000a7e3  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000a7ea  mov     r8, rdi; lpMem
0x18000a7ed  xor     edx, edx; dwFlags
0x18000a7ef  mov     rcx, rax; hHeap
0x18000a7f2  call    cs:__imp_HeapFree
0x18000a7f8  nop
0x18000a7f9  test    [rbp+2F0h+var_368], 8
0x18000a7fd  jz      short loc_18000A82F
0x18000a7ff  mov     rdi, [rbp+2F0h+var_360]
0x18000a803  test    rdi, rdi
0x18000a806  jz      short loc_18000A82F
0x18000a808  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000a80f  test    rax, rax
0x18000a812  jnz     short loc_18000A821
0x18000a814  call    cs:__imp_GetProcessHeap
0x18000a81a  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000a821  mov     r8, rdi; lpMem
0x18000a824  xor     edx, edx; dwFlags
0x18000a826  mov     rcx, rax; hHeap
0x18000a829  call    cs:__imp_HeapFree
0x18000a82f  mov     byte ptr [rsp+3F0h+var_3D0], bl
0x18000a833  mov     r8d, 1; unsigned int
0x18000a839  lea     rdx, [rsp+3F0h+var_3D0]; Src
0x18000a83e  lea     rcx, [rsp+3F0h+var_3C0]; this
0x18000a843  call    ?Write@WriteBuffer@@QEAAXPEAXI@Z; WriteBuffer::Write(void *,uint)
0x18000a848  test    bl, bl
0x18000a84a  jz      short loc_18000A86C
0x18000a84c  movaps  xmm0, [rsp+3F0h+var_388+8]
0x18000a851  movdqa  [rsp+3F0h+var_398+8], xmm0
0x18000a857  mov     r8d, 10h; unsigned int
0x18000a85d  lea     rdx, [rsp+3F0h+var_398+8]; Src
0x18000a862  lea     rcx, [rsp+3F0h+var_3C0]; this
0x18000a867  call    ?Write@WriteBuffer@@QEAAXPEAXI@Z; WriteBuffer::Write(void *,uint)
0x18000a86c  mov     eax, [r14+10h]
0x18000a870  mov     dword ptr [rsp+3F0h+Src], eax
0x18000a874  mov     r8d, 4; unsigned int
0x18000a87a  lea     rdx, [rsp+3F0h+Src]; Src
0x18000a87f  lea     rcx, [rsp+3F0h+var_3C0]; this
0x18000a884  call    ?Write@WriteBuffer@@QEAAXPEAXI@Z; WriteBuffer::Write(void *,uint)
0x18000a889  mov     r8, [r14+58h]; struct Image *
0x18000a88d  lea     rdx, [rsp+3F0h+var_3C0]; struct WriteBuffer *
0x18000a892  call    ?BinarySerializeImage@Configuration@@QEAAXAEAVWriteBuffer@@PEAVImage@@@Z; Configuration::BinarySerializeImage(WriteBuffer &,Image *)
0x18000a897  mov     rbx, [r14+68h]
0x18000a89b  test    rbx, rbx
0x18000a89e  setnz   byte ptr [rsp+3F0h+var_3D0]
0x18000a8a3  mov     r8d, 1; unsigned int
0x18000a8a9  lea     rdx, [rsp+3F0h+var_3D0]; Src
0x18000a8ae  lea     rcx, [rsp+3F0h+var_3C0]; this
0x18000a8b3  call    ?Write@WriteBuffer@@QEAAXPEAXI@Z; WriteBuffer::Write(void *,uint)
0x18000a8b8  test    rbx, rbx
0x18000a8bb  jz      short loc_18000A8D4
0x18000a8bd  mov     r8, [r14+68h]
0x18000a8c1  test    r8, r8
0x18000a8c4  jnz     short loc_18000A8CA
0x18000a8c6  mov     r8, [r14+58h]; struct Image *
0x18000a8ca  lea     rdx, [rsp+3F0h+var_3C0]; struct WriteBuffer *
0x18000a8cf  call    ?BinarySerializeImage@Configuration@@QEAAXAEAVWriteBuffer@@PEAVImage@@@Z; Configuration::BinarySerializeImage(WriteBuffer &,Image *)
0x18000a8d4  lea     r8, [r14+30h]
0x18000a8d8  lea     rdx, [rsp+3F0h+var_3C0]
0x18000a8dd  mov     rcx, rsi
0x18000a8e0  call    ?BinarySerializeDependencyList@Configuration@@QEAAXAEAVWriteBuffer@@PEAV?$SArray@PEAVLogicalImage@@$00@@@Z; Configuration::BinarySerializeDependencyList(WriteBuffer &,SArray<LogicalImage *,1> *)
0x18000a8e5  lea     r8, [r14+18h]
0x18000a8e9  lea     rdx, [rsp+3F0h+var_3C0]
0x18000a8ee  mov     rcx, rsi
0x18000a8f1  call    ?BinarySerializeDependencyList@Configuration@@QEAAXAEAVWriteBuffer@@PEAV?$SArray@PEAVLogicalImage@@$00@@@Z; Configuration::BinarySerializeDependencyList(WriteBuffer &,SArray<LogicalImage *,1> *)
0x18000a8f6  add     r15, 8
0x18000a8fa  sub     r12, 1
0x18000a8fe  jnz     loc_18000A5D8
0x18000a904  mov     [rsp+3F0h+var_3A8], r13
0x18000a909  mov     [rsp+3F0h+var_3A0], r13d
0x18000a90e  lea     rdx, [rsp+3F0h+var_3A8]
0x18000a913  mov     rcx, rsi
0x18000a916  call    ?GetRegKeyThrowing@Node@@QEAAXAEAV?$NewHolder@VKey@IRegWrapper@@@@@Z; Node::GetRegKeyThrowing(NewHolder<IRegWrapper::Key> &)
0x18000a91b  mov     rcx, [rsp+3F0h+var_3A8]
0x18000a920  mov     rax, [rcx]
0x18000a923  lea     r8, [rsp+3F0h+var_3C0]
0x18000a928  lea     rdx, aImagelist; "ImageList"
0x18000a92f  mov     rax, [rax+38h]
0x18000a933  call    cs:__guard_dispatch_icall_fptr
0x18000a939  nop
0x18000a93a  cmp     [rsp+3F0h+var_3A0], r13d
0x18000a93f  jz      short loc_18000A961
0x18000a941  mov     rcx, [rsp+3F0h+var_3A8]
0x18000a946  test    rcx, rcx
0x18000a949  jz      short loc_18000A95C
0x18000a94b  mov     rax, [rcx]
0x18000a94e  mov     edx, 1
0x18000a953  mov     rax, [rax]
0x18000a956  call    cs:__guard_dispatch_icall_fptr
0x18000a95c  mov     [rsp+3F0h+var_3A0], r13d
0x18000a961  test    byte ptr [rsp+3F0h+var_3B8], 8
0x18000a966  jz      short loc_18000A999
0x18000a968  mov     rbx, [rsp+3F0h+var_3B0]
0x18000a96d  test    rbx, rbx
0x18000a970  jz      short loc_18000A999
0x18000a972  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000a979  test    rax, rax
0x18000a97c  jnz     short loc_18000A98B
0x18000a97e  call    cs:__imp_GetProcessHeap
0x18000a984  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000a98b  mov     r8, rbx; lpMem
0x18000a98e  xor     edx, edx; dwFlags
0x18000a990  mov     rcx, rax; hHeap
0x18000a993  call    cs:__imp_HeapFree
0x18000a999  mov     rcx, [rbp+2F0h+var_30]
0x18000a9a0  xor     rcx, rsp; StackCookie
0x18000a9a3  call    __security_check_cookie
0x18000a9a8  lea     r11, [rsp+3F0h+var_20]
0x18000a9b0  mov     rbx, [r11+38h]
0x18000a9b4  mov     rsi, [r11+40h]
0x18000a9b8  mov     rdi, [r11+48h]
0x18000a9bc  mov     rsp, r11
0x18000a9bf  pop     r15
0x18000a9c1  pop     r14
0x18000a9c3  pop     r13
0x18000a9c5  pop     r12
0x18000a9c7  pop     rbp
0x18000a9c8  retn
```
