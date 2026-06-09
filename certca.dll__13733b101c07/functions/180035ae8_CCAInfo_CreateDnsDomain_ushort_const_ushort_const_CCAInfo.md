# CCAInfo::CreateDnsDomain(ushort const *,ushort const *,CCAInfo * *)

- ea: `0x180035ae8`
- end: `0x180035bc8`
- name: `?CreateDnsDomain@CCAInfo@@SAJPEBG0PEAPEAV1@@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct CCAInfo **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002dc00`

## callees

- `0x180008400`
- `0x18000a3b0`
- `0x18002a04c`
- `0x1800356b8`
- `0x180035ae8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035b48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180035b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035bb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035bb7`

## pseudocode

```c
__int64 __fastcall CCAInfo::CreateDnsDomain(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct CCAInfo **a3)
{
  unsigned __int16 *v3; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // edx
  unsigned int v10; // ecx
  SIZE_T v11; // rdx
  unsigned __int16 *v12; // rax
  int v13; // eax
  int v14; // eax
  unsigned int v16; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  if ( a2 )
  {
    v16 = 0;
    v7 = DNStoRFC1779Name(0, &v16, a2);
    if ( v7 != 122 )
    {
      v8 = myHError(v7);
      v9 = v8;
      v10 = 96207653;
LABEL_4:
      CSPrintErrorLineFile(v10, v9);
      return v8;
    }
    v11 = 2LL * ++v16;
    v12 = (unsigned __int16 *)LocalAlloc(0, v11);
    v3 = v12;
    if ( !v12 )
    {
      v8 = -2147024882;
      v10 = 96666405;
      v9 = -2147024882;
      goto LABEL_4;
    }
    v13 = DNStoRFC1779Name(v12, &v16, a2);
    if ( v13 )
    {
      v8 = myHError(v13);
      CSPrintErrorLineFile(0x5C90325u, v8);
LABEL_12:
      LocalFree(v3);
      return v8;
    }
  }
  v14 = CCAInfo::Create(a1, v3, a3);
  v8 = v14;
  if ( v14 )
    CSPrintErrorLineFile(0x5CD0325u, v14);
  if ( v3 )
    goto LABEL_12;
  return v8;
}

```

## disassembly

```asm
0x180035ae8  push    rbx
0x180035aea  push    rbp
0x180035aeb  push    rsi
0x180035aec  push    rdi
0x180035aed  sub     rsp, 28h
0x180035af1  xor     edi, edi
0x180035af3  mov     rsi, r8
0x180035af6  mov     rbx, rdx
0x180035af9  mov     rbp, rcx
0x180035afc  test    rdx, rdx
0x180035aff  jz      loc_180035B8F
0x180035b05  mov     r8, rdx; unsigned __int16 *
0x180035b08  mov     [rsp+48h+arg_8], edi
0x180035b0c  lea     rdx, [rsp+48h+arg_8]; unsigned int *
0x180035b11  xor     ecx, ecx; unsigned __int16 *
0x180035b13  call    ?DNStoRFC1779Name@@YAKPEAGPEAKPEBG@Z; DNStoRFC1779Name(ushort *,ulong *,ushort const *)
0x180035b18  cmp     eax, 7Ah ; 'z'
0x180035b1b  jz      short loc_180035B37
0x180035b1d  mov     ecx, eax; int
0x180035b1f  call    ?myHError@@YAJJ@Z; myHError(long)
0x180035b24  mov     ebx, eax
0x180035b26  mov     edx, eax; int
0x180035b28  mov     ecx, 5BC0325h; unsigned int
0x180035b2d  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035b32  jmp     loc_180035BBD
0x180035b37  mov     eax, [rsp+48h+arg_8]
0x180035b3b  xor     ecx, ecx; uFlags
0x180035b3d  inc     eax
0x180035b3f  mov     edx, eax
0x180035b41  add     rdx, rdx; uBytes
0x180035b44  mov     [rsp+48h+arg_8], eax
0x180035b48  call    cs:__imp_LocalAlloc
0x180035b4e  mov     rdi, rax
0x180035b51  test    rax, rax
0x180035b54  jnz     short loc_180035B64
0x180035b56  mov     ebx, 8007000Eh
0x180035b5b  mov     ecx, 5C30325h
0x180035b60  mov     edx, ebx
0x180035b62  jmp     short loc_180035B2D
0x180035b64  mov     r8, rbx; unsigned __int16 *
0x180035b67  lea     rdx, [rsp+48h+arg_8]; unsigned int *
0x180035b6c  mov     rcx, rax; unsigned __int16 *
0x180035b6f  call    ?DNStoRFC1779Name@@YAKPEAGPEAKPEBG@Z; DNStoRFC1779Name(ushort *,ulong *,ushort const *)
0x180035b74  test    eax, eax
0x180035b76  jz      short loc_180035B8F
0x180035b78  mov     ecx, eax; int
0x180035b7a  call    ?myHError@@YAJJ@Z; myHError(long)
0x180035b7f  mov     edx, eax; int
0x180035b81  mov     ecx, 5C90325h; unsigned int
0x180035b86  mov     ebx, eax
0x180035b88  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035b8d  jmp     short loc_180035BB4
0x180035b8f  mov     r8, rsi; struct CCAInfo **
0x180035b92  mov     rdx, rdi; Src
0x180035b95  mov     rcx, rbp; unsigned __int16 *
0x180035b98  call    ?Create@CCAInfo@@SAJPEBG0PEAPEAV1@@Z; CCAInfo::Create(ushort const *,ushort const *,CCAInfo * *)
0x180035b9d  mov     ebx, eax
0x180035b9f  test    eax, eax
0x180035ba1  jz      short loc_180035BAF
0x180035ba3  mov     edx, eax; int
0x180035ba5  mov     ecx, 5CD0325h; unsigned int
0x180035baa  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180035baf  test    rdi, rdi
0x180035bb2  jz      short loc_180035BBD
0x180035bb4  mov     rcx, rdi; hMem
0x180035bb7  call    cs:__imp_LocalFree
0x180035bbd  mov     eax, ebx
0x180035bbf  add     rsp, 28h
0x180035bc3  pop     rdi
0x180035bc4  pop     rsi
0x180035bc5  pop     rbp
0x180035bc6  pop     rbx
0x180035bc7  retn
```
