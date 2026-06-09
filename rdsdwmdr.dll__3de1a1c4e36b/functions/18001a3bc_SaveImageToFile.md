# SaveImageToFile

- ea: `0x18001a3bc`
- end: `0x18001a5eb`
- name: `SaveImageToFile`
- size: `559`
- prototype: `char __fastcall(struct PixelMap *, wchar_t *FileName, __int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180006240`

## callees

- `0x180004130`
- `0x180004324`
- `0x180004b9c`
- `0x1800083a0`
- `0x18001a2f0`
- `0x18001a3bc`
- `0x18002b960`

## import_xrefs

- `msvcrt!_wfopen_s` at `0x18001a52c`
- `msvcrt!_wfopen_s` at `0x18001a52c`
- `msvcrt!fclose` at `0x18001a5a0`
- `msvcrt!fclose` at `0x18001a5a0`
- `msvcrt!fwrite` at `0x18001a54d`
- `msvcrt!fwrite` at `0x18001a56b`
- `msvcrt!fwrite` at `0x18001a593`
- `msvcrt!fwrite` at `0x18001a54d`
- `msvcrt!fwrite` at `0x18001a56b`
- `msvcrt!fwrite` at `0x18001a593`

## pseudocode

```c
char __fastcall SaveImageToFile(struct PixelMap *a1, wchar_t *FileName, __int64 a3, int a4)
{
  int v6; // edx
  int v7; // ecx
  unsigned int v8; // edi
  unsigned int v9; // eax
  int v10; // eax
  int v11; // esi
  size_t v12; // rbx
  size_t v13; // rbx
  unsigned __int8 *StartPtr; // rax
  size_t v15; // r10
  size_t v16; // rbx
  unsigned __int8 v18; // [rsp+28h] [rbp-61h]
  int v19; // [rsp+38h] [rbp-51h]
  int v20; // [rsp+40h] [rbp-49h]
  FILE *Stream; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v22[2]; // [rsp+68h] [rbp-21h] BYREF
  int v23[2]; // [rsp+70h] [rbp-19h]
  unsigned __int8 *v24[2]; // [rsp+78h] [rbp-11h]
  __int16 Buffer; // [rsp+88h] [rbp-1h] BYREF
  unsigned int v26; // [rsp+8Ah] [rbp+1h]
  int v27; // [rsp+8Eh] [rbp+5h]
  int v28; // [rsp+92h] [rbp+9h]
  _DWORD v29[3]; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v30; // [rsp+A4h] [rbp+1Bh]
  unsigned int v31; // [rsp+ACh] [rbp+23h]
  __int64 v32; // [rsp+B0h] [rbp+27h]
  __int64 v33; // [rsp+B8h] [rbp+2Fh]

  v6 = *((_DWORD *)a1 + 3);
  if ( v6 != 15 && (((v6 + 1) & 0xF8) == 0x20 || (((_BYTE)v6 + 1) & 0xF8) == 0x18) )
  {
    *(_QWORD *)v22 = 0;
    *(_QWORD *)v23 = 0;
    *(_OWORD *)v24 = 0;
    if ( v6 != 24
      || (v7 = *((_DWORD *)a1 + 2), *((_DWORD *)a1 + 2) % 4)
      || (a4 = *(_DWORD *)a1, (unsigned int)(v7 - *(_DWORD *)a1) >= 4) )
    {
      PixelMap::SetupImage(
        (PixelMap *)v22,
        *(_DWORD *)a1,
        *((_DWORD *)a1 + 1),
        a4,
        -((3 * (*(_DWORD *)a1 + 1)) & 0xFFFFFFFC),
        v18);
      PixelMap::CopyFrom((PixelMap *)v22, a1);
    }
    else
    {
      PixelMap::AttachInternal((PixelMap *)v22, *((_DWORD *)a1 + 1), v7, 24, v19, v20, a4, *((_DWORD *)a1 + 1));
    }
    v8 = v22[1];
    v29[1] = v22[0];
    v29[0] = 40;
    if ( v23[0] <= 0 )
    {
      v10 = -v22[1];
      if ( (int)v22[1] > 0 )
        v10 = v22[1];
    }
    else
    {
      v9 = -v22[1];
      if ( (int)v22[1] > 0 )
        v9 = v22[1];
      v10 = -v9;
    }
    v29[2] = v10;
    v30 = 1572865;
    Buffer = 19778;
    v11 = -v23[0];
    v32 = 0;
    if ( v23[0] > 0 )
      v11 = v23[0];
    v33 = 0;
    v28 = 54;
    v31 = v22[1] * v11;
    v26 = v22[1] * v11 + 54;
    v27 = 0;
    Stream = 0;
    if ( !_wfopen_s(&Stream, FileName, L"wb") && Stream )
    {
      v12 = fwrite(&Buffer, 1u, 0xEu, Stream);
      v13 = fwrite(v29, 1u, 0x28u, Stream) + v12;
      StartPtr = PixelMap::GetStartPtr(v24[1], v8, v23[0]);
      v16 = fwrite(StartPtr, 1u, v15, Stream) + v13;
      fclose(Stream);
      LOBYTE(v16) = v16 == v26;
      PixelMap::~PixelMap((PixelMap *)v22);
      return v16;
    }
    PixelMap::~PixelMap((PixelMap *)v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a3bc  mov     [rsp-8+arg_10], rbx
0x18001a3c1  mov     [rsp-8+arg_18], rsi
0x18001a3c6  push    rbp
0x18001a3c7  push    rdi
0x18001a3c8  push    r15
0x18001a3ca  lea     rbp, [rsp-47h]
0x18001a3cf  sub     rsp, 0D0h
0x18001a3d6  mov     rax, cs:__security_cookie
0x18001a3dd  xor     rax, rsp
0x18001a3e0  mov     [rbp+57h+var_20], rax
0x18001a3e4  mov     r15, rdx
0x18001a3e7  mov     rbx, rcx
0x18001a3ea  mov     edx, [rcx+0Ch]
0x18001a3ed  cmp     edx, 0Fh
0x18001a3f0  jz      loc_18001A5C5
0x18001a3f6  lea     ecx, [rdx+1]
0x18001a3f9  mov     r8d, 0F8h
0x18001a3ff  mov     eax, ecx
0x18001a401  mov     esi, 18h
0x18001a406  and     eax, r8d
0x18001a409  cmp     eax, 20h ; ' '
0x18001a40c  jz      short loc_18001A419
0x18001a40e  and     ecx, r8d
0x18001a411  cmp     ecx, esi
0x18001a413  jnz     loc_18001A5C5
0x18001a419  mov     qword ptr [rbp+57h+var_78], 0
0x18001a421  xorps   xmm0, xmm0
0x18001a424  mov     qword ptr [rbp+57h+var_70], 0
0x18001a42c  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x18001a431  cmp     edx, esi
0x18001a433  jnz     short loc_18001A480
0x18001a435  mov     ecx, [rbx+8]
0x18001a438  mov     r8d, 4
0x18001a43e  mov     eax, ecx
0x18001a440  cdq
0x18001a441  idiv    r8d
0x18001a444  test    edx, edx
0x18001a446  jnz     short loc_18001A480
0x18001a448  mov     r9d, [rbx]
0x18001a44b  mov     eax, ecx
0x18001a44d  sub     eax, r9d
0x18001a450  cmp     eax, r8d
0x18001a453  jnb     short loc_18001A480
0x18001a455  mov     eax, [rbx+4]
0x18001a458  lea     rdx, [rbx+10h]
0x18001a45c  mov     r8, [rbx+18h]
0x18001a460  mov     [rsp+0E0h+var_90], eax; int
0x18001a464  mov     [rsp+0E0h+var_98], r9d; int
0x18001a469  mov     [rsp+0E0h+var_B0], esi; int
0x18001a46d  mov     dword ptr [rsp+0E0h+var_B8], ecx; int
0x18001a471  lea     rcx, [rbp+57h+var_78]; this
0x18001a475  mov     [rsp+0E0h+var_C0], eax; unsigned int
0x18001a479  call    ?AttachInternal@PixelMap@@AEAA_NAEBV?$TCntPtr@VRefCountedBuffer@@@@PEAEHHHW4RdpPixelFormat@@HHHH@Z; PixelMap::AttachInternal(TCntPtr<RefCountedBuffer> const &,uchar *,int,int,int,RdpPixelFormat,int,int,int,int)
0x18001a47e  jmp     short loc_18001A4AA
0x18001a480  mov     edx, [rbx]; int
0x18001a482  mov     r8d, [rbx+4]; int
0x18001a486  lea     eax, [rdx+1]
0x18001a489  lea     ecx, [rax+rax*2]
0x18001a48c  and     ecx, 0FFFFFFFCh
0x18001a48f  neg     ecx
0x18001a491  mov     [rsp+0E0h+var_C0], ecx; int
0x18001a495  lea     rcx, [rbp+57h+var_78]; this
0x18001a499  call    ?SetupImage@PixelMap@@QEAA_NHHHHE@Z; PixelMap::SetupImage(int,int,int,int,uchar)
0x18001a49e  mov     rdx, rbx; struct PixelMap *
0x18001a4a1  lea     rcx, [rbp+57h+var_78]; this
0x18001a4a5  call    ?CopyFrom@PixelMap@@QEAA_NAEBV1@@Z; PixelMap::CopyFrom(PixelMap const &)
0x18001a4aa  cmp     [rbp+57h+var_70], 0
0x18001a4ae  mov     eax, [rbp+57h+var_78]
0x18001a4b1  mov     edi, [rbp+57h+var_78+4]
0x18001a4b4  mov     [rbp+57h+var_44], eax
0x18001a4b7  mov     eax, edi
0x18001a4b9  mov     [rbp+57h+var_48], 28h ; '('
0x18001a4c0  jle     short loc_18001A4CB
0x18001a4c2  neg     eax
0x18001a4c4  cmovs   eax, edi
0x18001a4c7  neg     eax
0x18001a4c9  jmp     short loc_18001A4D0
0x18001a4cb  neg     eax
0x18001a4cd  cmovs   eax, edi
0x18001a4d0  mov     esi, [rbp+57h+var_70]
0x18001a4d3  lea     r8, aWb; "wb"
0x18001a4da  mov     [rbp+57h+var_40], eax
0x18001a4dd  lea     rcx, [rbp+57h+Stream]; Stream
0x18001a4e1  mov     eax, 4D42h
0x18001a4e6  mov     [rbp+57h+var_3C], 180001h
0x18001a4ee  mov     [rbp+57h+Buffer], ax
0x18001a4f2  neg     esi
0x18001a4f4  mov     rdx, r15; FileName
0x18001a4f7  mov     [rbp+57h+var_30], 0
0x18001a4ff  cmovs   esi, [rbp+57h+var_70]
0x18001a503  mov     ebx, 1
0x18001a508  imul    esi, edi
0x18001a50b  mov     [rbp+57h+var_28], 0
0x18001a513  mov     [rbp+57h+var_4E], 36h ; '6'
0x18001a51a  mov     [rbp+57h+var_34], esi
0x18001a51d  lea     eax, [rsi+36h]
0x18001a520  mov     [rbp+57h+var_56], eax
0x18001a523  xor     eax, eax
0x18001a525  mov     [rbp+57h+var_52], eax
0x18001a528  mov     [rbp+57h+Stream], rax
0x18001a52c  call    cs:__imp__wfopen_s
0x18001a532  test    eax, eax
0x18001a534  jnz     loc_18001A5BC
0x18001a53a  mov     r9, [rbp+57h+Stream]; Stream
0x18001a53e  test    r9, r9
0x18001a541  jz      short loc_18001A5BC
0x18001a543  lea     r8d, [rbx+0Dh]; ElementCount
0x18001a547  mov     edx, ebx; ElementSize
0x18001a549  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001a54d  call    cs:__imp_fwrite
0x18001a553  mov     r9, [rbp+57h+Stream]; Stream
0x18001a557  lea     rcx, [rbp+57h+var_48]; Buffer
0x18001a55b  mov     r8d, 28h ; '('; ElementCount
0x18001a561  mov     rbx, rax
0x18001a564  lea     r15d, [r8-27h]
0x18001a568  mov     edx, r15d; ElementSize
0x18001a56b  call    cs:__imp_fwrite
0x18001a571  mov     rcx, [rbp+57h+var_68+8]; unsigned __int8 *
0x18001a575  mov     edx, edi; unsigned int
0x18001a577  mov     r8d, [rbp+57h+var_70]; int
0x18001a57b  add     rbx, rax
0x18001a57e  movsxd  r10, esi
0x18001a581  call    ?GetStartPtr@PixelMap@@SAPEAEPEAEIH@Z; PixelMap::GetStartPtr(uchar *,uint,int)
0x18001a586  mov     r9, [rbp+57h+Stream]; Stream
0x18001a58a  mov     rcx, rax; Buffer
0x18001a58d  mov     r8, r10; ElementCount
0x18001a590  mov     edx, r15d; ElementSize
0x18001a593  call    cs:__imp_fwrite
0x18001a599  mov     rcx, [rbp+57h+Stream]; Stream
0x18001a59d  add     rbx, rax
0x18001a5a0  call    cs:__imp_fclose
0x18001a5a6  mov     eax, [rbp+57h+var_56]
0x18001a5a9  lea     rcx, [rbp+57h+var_78]; this
0x18001a5ad  cmp     rbx, rax
0x18001a5b0  setz    bl
0x18001a5b3  call    ??1PixelMap@@QEAA@XZ; PixelMap::~PixelMap(void)
0x18001a5b8  mov     al, bl
0x18001a5ba  jmp     short loc_18001A5C7
0x18001a5bc  lea     rcx, [rbp+57h+var_78]; this
0x18001a5c0  call    ??1PixelMap@@QEAA@XZ; PixelMap::~PixelMap(void)
0x18001a5c5  xor     al, al
0x18001a5c7  mov     rcx, [rbp+57h+var_20]
0x18001a5cb  xor     rcx, rsp; StackCookie
0x18001a5ce  call    __security_check_cookie
0x18001a5d3  lea     r11, [rsp+0E0h+var_10]
0x18001a5db  mov     rbx, [r11+30h]
0x18001a5df  mov     rsi, [r11+38h]
0x18001a5e3  mov     rsp, r11
0x18001a5e6  pop     r15
0x18001a5e8  pop     rdi
0x18001a5e9  pop     rbp
0x18001a5ea  retn
```
