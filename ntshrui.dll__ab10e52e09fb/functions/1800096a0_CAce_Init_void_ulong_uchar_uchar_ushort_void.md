# CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)

- ea: `0x1800096a0`
- end: `0x180009824`
- name: `?_Init@CAce@@AEAAJPEAXKEEG0@Z`
- size: `388`
- prototype: `int(CAce *__hidden this, void *, unsigned int, unsigned __int8, unsigned __int8, unsigned __int16, void *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a800`
- `0x18000ac90`
- `0x18000b240`
- `0x18000b6f0`
- `0x18000c6f0`
- `0x18000f4f0`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18002637c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800096e1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800096e1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000971e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000971e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800096f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800097e0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800096f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800097e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009707`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009801`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009707`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009801`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800097cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800097cb`
- `ntdll!RtlMapGenericMask` at `0x180009768`
- `ntdll!RtlMapGenericMask` at `0x180009768`

## pseudocode

```c
__int64 __fastcall CAce::_Init(
        CAce *this,
        void *a2,
        int a3,
        char a4,
        unsigned __int8 a5,
        unsigned __int16 a6,
        void *Src)
{
  unsigned int v11; // ebx
  DWORD LengthSid; // r14d
  HLOCAL v13; // rax
  void *v14; // rbp
  int Error; // r14d
  char v16; // cl
  unsigned int v17; // eax
  DWORD v19; // edx
  HLOCAL v20; // rax

  if ( a2 )
  {
    v11 = -2147024809;
    *((_QWORD *)this + 1) = 0;
    if ( !IsValidSid(a2) )
      return v11;
    LengthSid = GetLengthSid(a2);
    v11 = -2147024882;
    v13 = LocalAlloc(0x40u, LengthSid);
    v14 = v13;
    if ( !v13 )
      return v11;
    if ( CopySid(LengthSid, v13, a2) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        LocalFree(v14);
        return (unsigned int)Error;
      }
    }
    *((_QWORD *)this + 1) = v14;
    if ( !Src )
      goto LABEL_7;
    v19 = GetLengthSid(a2) + 8;
    if ( a6 <= v19 )
      goto LABEL_7;
    *((_DWORD *)this + 6) = a6 - v19;
    v20 = LocalAlloc(0x40u, a6 - v19);
    *((_QWORD *)this + 2) = v20;
    if ( v20 )
    {
      memcpy_0(v20, Src, *((unsigned int *)this + 6));
LABEL_7:
      *(_BYTE *)this = a5;
      *((_DWORD *)this + 1) = a3;
      *((_BYTE *)this + 1) = a4;
      *((_WORD *)this + 1) = a6;
      RtlMapGenericMask((PACCESS_MASK)this + 1, (PGENERIC_MAPPING)&GenericMapping);
      v16 = *(_BYTE *)this;
      v17 = 0x80000000;
      *((_DWORD *)this + 7) = 0x80000000;
      if ( !v16 || v16 == 9 )
      {
        v17 = -2147483647;
        *((_DWORD *)this + 7) = -2147483647;
      }
      v11 = Error;
      if ( (*((_BYTE *)this + 1) & 0x10) != 0 )
        *((_DWORD *)this + 7) = v17 | 0x20;
    }
    return v11;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800096a0  push    rbx
0x1800096a2  push    rsi
0x1800096a3  push    rdi
0x1800096a4  push    r12
0x1800096a6  push    r13
0x1800096a8  sub     rsp, 20h
0x1800096ac  movzx   r12d, r9b
0x1800096b0  mov     r13d, r8d
0x1800096b3  mov     rsi, rdx
0x1800096b6  mov     rdi, rcx
0x1800096b9  test    rdx, rdx
0x1800096bc  jz      loc_1800097D6
0x1800096c2  mov     [rsp+48h+arg_0], rbp
0x1800096c7  mov     ebx, 80070057h
0x1800096cc  mov     qword ptr [rcx+8], 0
0x1800096d4  mov     rcx, rdx; pSid
0x1800096d7  mov     [rsp+48h+arg_8], r14
0x1800096dc  mov     [rsp+48h+arg_10], r15
0x1800096e1  call    cs:__imp_IsValidSid
0x1800096e7  test    eax, eax
0x1800096e9  jz      loc_180009794
0x1800096ef  mov     rcx, rsi; pSid
0x1800096f2  call    cs:__imp_GetLengthSid
0x1800096f8  mov     edx, eax; uBytes
0x1800096fa  mov     ecx, 40h ; '@'; uFlags
0x1800096ff  mov     r14d, eax
0x180009702  mov     ebx, 8007000Eh
0x180009707  call    cs:__imp_LocalAlloc
0x18000970d  mov     rbp, rax
0x180009710  test    rax, rax
0x180009713  jz      short loc_180009794
0x180009715  mov     r8, rsi; pSourceSid
0x180009718  mov     rdx, rax; pDestinationSid
0x18000971b  mov     ecx, r14d; nDestinationSidLength
0x18000971e  call    cs:__imp_CopySid
0x180009724  test    eax, eax
0x180009726  jz      loc_1800097B8
0x18000972c  xor     r14d, r14d
0x18000972f  movzx   r15d, [rsp+48h+arg_28]
0x180009735  mov     [rdi+8], rbp
0x180009739  mov     rbp, [rsp+48h+Src]
0x180009741  test    rbp, rbp
0x180009744  jnz     loc_1800097DD
0x18000974a  movzx   eax, [rsp+48h+arg_20]
0x18000974f  lea     rcx, [rdi+4]; AccessMask
0x180009753  lea     rdx, GenericMapping; GenericMapping
0x18000975a  mov     [rdi], al
0x18000975c  mov     [rcx], r13d
0x18000975f  mov     [rdi+1], r12b
0x180009763  mov     [rdi+2], r15w
0x180009768  call    cs:__imp_RtlMapGenericMask
0x18000976e  movzx   ecx, byte ptr [rdi]
0x180009771  mov     eax, 80000000h
0x180009776  mov     [rdi+1Ch], eax
0x180009779  test    cl, cl
0x18000977b  jnz     short loc_1800097B1
0x18000977d  mov     eax, 80000001h
0x180009782  mov     [rdi+1Ch], eax
0x180009785  test    byte ptr [rdi+1], 10h
0x180009789  mov     ebx, r14d
0x18000978c  jz      short loc_180009794
0x18000978e  or      eax, 20h
0x180009791  mov     [rdi+1Ch], eax
0x180009794  mov     r15, [rsp+48h+arg_10]
0x180009799  mov     eax, ebx
0x18000979b  mov     r14, [rsp+48h+arg_8]
0x1800097a0  mov     rbp, [rsp+48h+arg_0]
0x1800097a5  add     rsp, 20h
0x1800097a9  pop     r13
0x1800097ab  pop     r12
0x1800097ad  pop     rdi
0x1800097ae  pop     rsi
0x1800097af  pop     rbx
0x1800097b0  retn
0x1800097b1  cmp     cl, 9
0x1800097b4  jnz     short loc_180009785
0x1800097b6  jmp     short loc_18000977D
0x1800097b8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800097bd  mov     r14d, eax
0x1800097c0  test    eax, eax
0x1800097c2  jns     loc_18000972F
0x1800097c8  mov     rcx, rbp; hMem
0x1800097cb  call    cs:__imp_LocalFree
0x1800097d1  mov     ebx, r14d
0x1800097d4  jmp     short loc_180009794
0x1800097d6  mov     eax, 80070057h
0x1800097db  jmp     short loc_1800097A5
0x1800097dd  mov     rcx, rsi; pSid
0x1800097e0  call    cs:__imp_GetLengthSid
0x1800097e6  lea     edx, [rax+8]
0x1800097e9  mov     eax, r15d
0x1800097ec  cmp     r15d, edx
0x1800097ef  jbe     loc_18000974A
0x1800097f5  sub     eax, edx
0x1800097f7  mov     ecx, 40h ; '@'; uFlags
0x1800097fc  mov     edx, eax; uBytes
0x1800097fe  mov     [rdi+18h], edx
0x180009801  call    cs:__imp_LocalAlloc
0x180009807  mov     [rdi+10h], rax
0x18000980b  test    rax, rax
0x18000980e  jz      short loc_180009794
0x180009810  mov     r8d, [rdi+18h]; Size
0x180009814  mov     rdx, rbp; Src
0x180009817  mov     rcx, rax; void *
0x18000981a  call    memcpy_0
0x18000981f  jmp     loc_18000974A
```
