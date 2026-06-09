# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x1800069c0`
- end: `0x180006b4e`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002440`
- `0x1800063e0`

## callees

- `0x1800069c0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800069fe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006a09`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006a17`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800069fe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006a09`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006a17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006a9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006aa7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006af8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006a9d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006aa7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006af8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax

  if ( !a1 )
    return 2147942487LL;
  *((_QWORD *)a1 + 4) = a2;
  *((_QWORD *)a1 + 2) = a3;
  *((_QWORD *)a1 + 3) = a3;
  *((_QWORD *)a1 + 1) = a3;
  *((_DWORD *)a1 + 10) = 0;
  *((_QWORD *)a1 + 6) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 56));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 96));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 136));
  *((_QWORD *)a1 + 23) = 0;
  *((_BYTE *)a1 + 192) = 1;
  *((_DWORD *)a1 + 52) = 0;
  *((_DWORD *)a1 + 56) = 0;
  *((_QWORD *)a1 + 27) = 0;
  *((_QWORD *)a1 + 29) = 0;
  v6 = *((_QWORD *)a1 + 4);
  if ( v6 && *(_QWORD *)v6 )
  {
    do
    {
      LOBYTE(v5) = 1;
      (*(void (__fastcall **)(__int64))(v6 + 64))(v5);
      if ( *(_DWORD *)a1 == 176 )
        v7 = 56;
      else
        v7 = 72;
      v6 += v7;
    }
    while ( *(_QWORD *)v6 );
  }
  *((_DWORD *)a1 + 60) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800069c0  mov     [rsp+arg_8], rbx
0x1800069c5  mov     [rsp+arg_0], rcx
0x1800069ca  push    rdi
0x1800069cb  sub     rsp, 20h
0x1800069cf  mov     rbx, rcx
0x1800069d2  test    rcx, rcx
0x1800069d5  jnz     short loc_1800069E1
0x1800069d7  mov     eax, 80070057h
0x1800069dc  jmp     loc_180006B43
0x1800069e1  mov     [rcx+20h], rdx
0x1800069e5  mov     [rcx+10h], r8
0x1800069e9  mov     [rcx+18h], r8
0x1800069ed  mov     [rcx+8], r8
0x1800069f1  xor     edi, edi
0x1800069f3  mov     [rcx+28h], edi
0x1800069f6  mov     [rcx+30h], rdi
0x1800069fa  add     rcx, 38h ; '8'; lpCriticalSection
0x1800069fe  call    cs:__imp_InitializeCriticalSection
0x180006a04  nop
0x180006a05  lea     rcx, [rbx+60h]; lpCriticalSection
0x180006a09  call    cs:__imp_InitializeCriticalSection
0x180006a0f  nop
0x180006a10  lea     rcx, [rbx+88h]; lpCriticalSection
0x180006a17  call    cs:__imp_InitializeCriticalSection
0x180006a1d  nop
0x180006a1e  mov     [rbx+0B8h], rdi
0x180006a25  mov     byte ptr [rbx+0C0h], 1
0x180006a2c  mov     [rbx+0D0h], edi
0x180006a32  mov     [rbx+0E0h], edi
0x180006a38  mov     [rbx+0D8h], rdi
0x180006a3f  mov     [rbx+0E8h], rdi
0x180006a46  mov     rdi, [rbx+20h]
0x180006a4a  test    rdi, rdi
0x180006a4d  jz      short loc_180006A7D
0x180006a4f  cmp     qword ptr [rdi], 0
0x180006a53  jz      short loc_180006A7D
0x180006a55  mov     cl, 1
0x180006a57  mov     rax, [rdi+40h]
0x180006a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a60  cmp     dword ptr [rbx], 0B0h
0x180006a66  jnz     short loc_180006A6F
0x180006a68  mov     eax, 38h ; '8'
0x180006a6d  jmp     short loc_180006A74
0x180006a6f  mov     eax, 48h ; 'H'
0x180006a74  add     rdi, rax
0x180006a77  cmp     qword ptr [rdi], 0
0x180006a7b  jnz     short loc_180006A55
0x180006a7d  mov     dword ptr [rbx+0F0h], 1
0x180006a87  xor     eax, eax
0x180006a89  mov     rbx, [rsp+28h+arg_8]
0x180006a8e  add     rsp, 20h
0x180006a92  pop     rdi
0x180006a93  retn
0x180006a94  mov     rbx, [rsp+28h+arg_0]
0x180006a99  lea     rcx, [rbx+60h]; lpCriticalSection
0x180006a9d  call    cs:__imp_DeleteCriticalSection
0x180006aa3  lea     rcx, [rbx+38h]; lpCriticalSection
0x180006aa7  call    cs:__imp_DeleteCriticalSection
0x180006aad  xorps   xmm0, xmm0
0x180006ab0  xor     eax, eax
0x180006ab2  movups  xmmword ptr [rbx+88h], xmm0
0x180006ab9  movups  xmmword ptr [rbx+98h], xmm0
0x180006ac0  mov     [rbx+0A8h], rax
0x180006ac7  xorps   xmm0, xmm0
0x180006aca  movups  xmmword ptr [rbx+60h], xmm0
0x180006ace  movups  xmmword ptr [rbx+70h], xmm0
0x180006ad2  mov     [rbx+80h], rax
0x180006ad9  xorps   xmm0, xmm0
0x180006adc  movups  xmmword ptr [rbx+38h], xmm0
0x180006ae0  movups  xmmword ptr [rbx+48h], xmm0
0x180006ae4  mov     [rbx+58h], rax
0x180006ae8  mov     eax, 0C0000017h
0x180006aed  jmp     short loc_180006B43
0x180006aef  mov     rbx, [rsp+28h+arg_0]
0x180006af4  lea     rcx, [rbx+38h]; lpCriticalSection
0x180006af8  call    cs:__imp_DeleteCriticalSection
0x180006afe  xorps   xmm0, xmm0
0x180006b01  xor     eax, eax
0x180006b03  movups  xmmword ptr [rbx+60h], xmm0
0x180006b07  movups  xmmword ptr [rbx+70h], xmm0
0x180006b0b  mov     [rbx+80h], rax
0x180006b12  xorps   xmm0, xmm0
0x180006b15  movups  xmmword ptr [rbx+38h], xmm0
0x180006b19  movups  xmmword ptr [rbx+48h], xmm0
0x180006b1d  mov     [rbx+58h], rax
0x180006b21  mov     eax, 0C0000017h
0x180006b26  jmp     short loc_180006B43
0x180006b28  mov     rax, [rsp+28h+arg_0]
0x180006b2d  xorps   xmm0, xmm0
0x180006b30  xor     ecx, ecx
0x180006b32  movups  xmmword ptr [rax+38h], xmm0
0x180006b36  movups  xmmword ptr [rax+48h], xmm0
0x180006b3a  mov     [rax+58h], rcx
0x180006b3e  mov     eax, 0C0000017h
0x180006b43  mov     rbx, [rsp+28h+arg_8]
0x180006b48  add     rsp, 20h
0x180006b4c  pop     rdi
0x180006b4d  retn
0x180055a10  push    rbp
0x180055a12  sub     rsp, 20h
0x180055a16  mov     rbp, rdx
0x180055a19  mov     rax, [rcx]
0x180055a1c  xor     ecx, ecx
0x180055a1e  cmp     dword ptr [rax], 0C0000017h
0x180055a24  setz    cl
0x180055a27  mov     eax, ecx
0x180055a29  add     rsp, 20h
0x180055a2d  pop     rbp
0x180055a2e  retn
0x180055a30  push    rbp
0x180055a32  sub     rsp, 20h
0x180055a36  mov     rbp, rdx
0x180055a39  mov     rax, [rcx]
0x180055a3c  xor     ecx, ecx
0x180055a3e  cmp     dword ptr [rax], 0C0000017h
0x180055a44  setz    cl
0x180055a47  mov     eax, ecx
0x180055a49  add     rsp, 20h
0x180055a4d  pop     rbp
0x180055a4e  retn
0x180055a50  push    rbp
0x180055a52  sub     rsp, 20h
0x180055a56  mov     rbp, rdx
0x180055a59  mov     rax, [rcx]
0x180055a5c  xor     ecx, ecx
0x180055a5e  cmp     dword ptr [rax], 0C0000017h
0x180055a64  setz    cl
0x180055a67  mov     eax, ecx
0x180055a69  add     rsp, 20h
0x180055a6d  pop     rbp
0x180055a6e  retn
```
