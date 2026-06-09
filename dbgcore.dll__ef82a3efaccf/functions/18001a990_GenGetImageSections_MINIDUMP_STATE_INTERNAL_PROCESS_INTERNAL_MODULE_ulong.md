# GenGetImageSections(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_MODULE *,ulong)

- ea: `0x18001a990`
- end: `0x18001ace9`
- name: `?GenGetImageSections@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_MODULE@@K@Z`
- size: `857`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, struct _INTERNAL_MODULE *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180005634`

## callees

- `0x180001710`
- `0x180016eec`
- `0x18001a990`
- `0x18001cdb0`
- `0x180026cb4`
- `0x18002c010`

## string_xrefs

- `0x18001aae8`: `GenGetImageSections.Read(0x%I64x, 0x%x) failed, 0x%08x`
- `0x18001ab35`: `GenGetImageSections.GenImageNtHeader(0x%I64x) failed`
- `0x18001ac52`: `GenGetImageSections.Section.Read(0x%I64x, 0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall GenGetImageSections(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_MODULE *a3,
        unsigned int a4)
{
  _QWORD *v6; // rsi
  __int64 result; // rax
  struct _INTERNAL_PROCESS *v8; // rdx
  char *v9; // rax
  unsigned int v10; // ebx
  struct _IMAGE_NT_HEADERS *v11; // rax
  struct _IMAGE_NT_HEADERS *v12; // r12
  char *v13; // r15
  unsigned int v14; // esi
  unsigned int v15; // eax
  signed __int64 v16; // r15
  unsigned int v17; // eax
  unsigned int v18; // eax
  struct _IMAGE_SECTION_HEADER *v19; // [rsp+20h] [rbp-328h]
  struct _IMAGE_SECTION_HEADER *v20; // [rsp+20h] [rbp-328h]
  void **v21; // [rsp+28h] [rbp-320h]
  void *v22; // [rsp+40h] [rbp-308h] BYREF
  int v23[5]; // [rsp+48h] [rbp-300h] BYREF
  unsigned int v24; // [rsp+5Ch] [rbp-2ECh]
  char *v25; // [rsp+60h] [rbp-2E8h]
  unsigned int v26; // [rsp+68h] [rbp-2E0h]
  unsigned int v27; // [rsp+78h] [rbp-2D0h]
  struct _INTERNAL_PROCESS *v28; // [rsp+90h] [rbp-2B8h]
  char *v29; // [rsp+98h] [rbp-2B0h]
  _QWORD *v30; // [rsp+A8h] [rbp-2A0h]
  _QWORD v31[4]; // [rsp+B0h] [rbp-298h] BYREF
  _IMAGE_SECTION_HEADER v32; // [rsp+D0h] [rbp-278h] BYREF
  _BYTE v33[512]; // [rsp+100h] [rbp-248h] BYREF

  v24 = a4;
  v28 = a2;
  v22 = 0;
  v23[0] = 0;
  v31[0] = &GenMiniDumpProviderCallbacks::`vftable';
  v31[1] = a1;
  v31[2] = a2;
  v31[3] = 4;
  v6 = (_QWORD *)((char *)a1 + 16);
  v29 = (char *)a1 + 16;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD *))(**((_QWORD **)a1 + 2)
                                                                                             + 136LL))(
             *((_QWORD *)a1 + 2),
             *((_QWORD *)a2 + 8),
             *((_QWORD *)a3 + 15),
             *((_QWORD *)a3 + 1),
             a4,
             v31);
  if ( (_DWORD)result )
  {
    v21 = &v22;
    LODWORD(v19) = 0;
    if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, int *, _QWORD))(*(_QWORD *)*v6 + 96LL))(
           *v6,
           *((_QWORD *)a3 + 15),
           v23,
           0)
      || !VerifyMapping(a1, v8, *((unsigned __int16 **)a3 + 15), v22, (unsigned __int64)v19, *((_QWORD *)a3 + 1)) )
    {
      v22 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *, int))(*(_QWORD *)*v6 + 240LL))(
              *v6,
              *(_QWORD *)a1,
              *((_QWORD *)a3 + 1),
              v33,
              512);
      if ( v10 )
      {
        *((_DWORD *)a1 + 44) |= 2u;
        LODWORD(v21) = v10;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
          *((_QWORD *)a1 + 5),
          4,
          "GenGetImageSections.Read(0x%I64x, 0x%x) failed, 0x%08x",
          *((_QWORD *)a3 + 1),
          512,
          v21);
        return v10;
      }
      v9 = v33;
    }
    else
    {
      v9 = (char *)v22;
    }
    v25 = v9;
    v30 = v6;
    v11 = GenImageNtHeader(v9, 0);
    v12 = v11;
    if ( v11 )
    {
      v10 = 0;
      v13 = (char *)&v11->OptionalHeader + v11->FileHeader.SizeOfOptionalHeader;
      if ( v22 )
      {
        v14 = 0;
        v26 = 0;
        while ( v14 < v12->FileHeader.NumberOfSections )
        {
          v15 = GenAddImageSection(a1, v28, a3, v24, (struct _IMAGE_SECTION_HEADER *)&v13[40 * v14]);
          if ( v15 )
            v10 = v15;
          v27 = v10;
          v26 = ++v14;
        }
        v6 = v29;
      }
      else
      {
        memset(&v32, 0, sizeof(v32));
        v16 = *((_QWORD *)a3 + 1) + v13 - v25;
        LODWORD(v25) = 0;
        if ( v11->FileHeader.NumberOfSections )
        {
          do
          {
            LODWORD(v20) = 40;
            v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, signed __int64, _IMAGE_SECTION_HEADER *, struct _IMAGE_SECTION_HEADER *))(*(_QWORD *)*v6 + 240LL))(
                    *v6,
                    *(_QWORD *)a1,
                    v16,
                    &v32,
                    v20);
            if ( v17 )
            {
              v10 = v17;
              LODWORD(v21) = v17;
              (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
                *((_QWORD *)a1 + 5),
                4,
                "GenGetImageSections.Section.Read(0x%I64x, 0x%x) failed, 0x%08x",
                v16,
                40,
                v21);
            }
            else
            {
              v18 = GenAddImageSection(a1, v28, a3, v24, &v32);
              if ( v18 )
                v10 = v18;
            }
            v16 += 40LL;
            LODWORD(v25) = (_DWORD)v25 + 1;
          }
          while ( (unsigned int)v25 < v12->FileHeader.NumberOfSections );
        }
      }
    }
    else
    {
      v10 = -2147023742;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "GenGetImageSections.GenImageNtHeader(0x%I64x) failed",
        *((_QWORD *)a3 + 1));
    }
    if ( v22 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 104LL))(*v6);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18001a990  mov     r11, rsp
0x18001a993  push    rbx
0x18001a994  push    rsi
0x18001a995  push    rdi
0x18001a996  push    r12
0x18001a998  push    r13
0x18001a99a  push    r14
0x18001a99c  push    r15
0x18001a99e  sub     rsp, 310h
0x18001a9a5  mov     rax, cs:__security_cookie
0x18001a9ac  xor     rax, rsp
0x18001a9af  mov     [rsp+348h+var_48], rax
0x18001a9b7  mov     [rsp+348h+var_2EC], r9d
0x18001a9bc  mov     r13, r8
0x18001a9bf  mov     [rsp+348h+var_2B8], rdx
0x18001a9c7  mov     r14, rcx
0x18001a9ca  xor     edi, edi
0x18001a9cc  mov     [rsp+348h+var_308], rdi
0x18001a9d1  mov     [rsp+348h+var_300], edi
0x18001a9d5  lea     rax, ??_7GenMiniDumpProviderCallbacks@@6B@; const GenMiniDumpProviderCallbacks::`vftable'
0x18001a9dc  mov     [r11-298h], rax
0x18001a9e3  mov     [r11-290h], rcx
0x18001a9ea  mov     [r11-288h], rdx
0x18001a9f1  mov     qword ptr [r11-280h], 4
0x18001a9fc  lea     rsi, [rcx+10h]
0x18001aa00  mov     [rsp+348h+var_2B0], rsi
0x18001aa08  mov     rcx, [rsi]
0x18001aa0b  mov     rax, [rcx]
0x18001aa0e  lea     r8, [r11-298h]
0x18001aa15  mov     [rsp+348h+var_320], r8
0x18001aa1a  mov     dword ptr [rsp+348h+var_328], r9d
0x18001aa1f  mov     r9, [r13+8]
0x18001aa23  mov     r8, [r13+78h]
0x18001aa27  mov     rdx, [rdx+40h]
0x18001aa2b  mov     rax, [rax+88h]
0x18001aa32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa37  test    eax, eax
0x18001aa39  jz      loc_18001ACC6
0x18001aa3f  mov     rcx, [rsi]
0x18001aa42  mov     rax, [rcx]
0x18001aa45  lea     rdx, [rsp+348h+var_308]
0x18001aa4a  mov     [rsp+348h+var_320], rdx
0x18001aa4f  mov     dword ptr [rsp+348h+var_328], edi; unsigned __int64
0x18001aa53  xor     r9d, r9d
0x18001aa56  lea     r8, [rsp+348h+var_300]
0x18001aa5b  mov     rdx, [r13+78h]
0x18001aa5f  mov     rax, [rax+60h]
0x18001aa63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa68  test    eax, eax
0x18001aa6a  jnz     short loc_18001AA91
0x18001aa6c  mov     rax, [r13+8]
0x18001aa70  mov     [rsp+348h+var_320], rax; unsigned __int64
0x18001aa75  mov     r9, [rsp+348h+var_308]; void *
0x18001aa7a  mov     r8, [r13+78h]; unsigned __int16 *
0x18001aa7e  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001aa81  call    ?VerifyMapping@@YA_NPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAGPEAX_K4@Z; VerifyMapping(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,ushort *,void *,unsigned __int64,unsigned __int64)
0x18001aa86  test    al, al
0x18001aa88  jz      short loc_18001AA91
0x18001aa8a  mov     rax, [rsp+348h+var_308]
0x18001aa8f  jmp     short loc_18001AB06
0x18001aa91  mov     [rsp+348h+var_308], rdi
0x18001aa96  mov     rcx, [rsi]
0x18001aa99  mov     rax, [rcx]
0x18001aa9c  mov     r15d, 200h
0x18001aaa2  mov     dword ptr [rsp+348h+var_328], r15d
0x18001aaa7  lea     r9, [rsp+348h+var_248]
0x18001aaaf  mov     r8, [r13+8]
0x18001aab3  mov     rdx, [r14]
0x18001aab6  mov     rax, [rax+0F0h]
0x18001aabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aac2  mov     ebx, eax
0x18001aac4  test    eax, eax
0x18001aac6  jz      short loc_18001AAFE
0x18001aac8  or      dword ptr [r14+0B0h], 2
0x18001aad0  mov     rcx, [r14+28h]
0x18001aad4  mov     r8, [rcx]
0x18001aad7  mov     rax, [r8+8]
0x18001aadb  mov     dword ptr [rsp+348h+var_320], ebx
0x18001aadf  mov     [rsp+348h+var_328], r15
0x18001aae4  mov     r9, [r13+8]
0x18001aae8  lea     r8, aGengetimagesec_1; "GenGetImageSections.Read(0x%I64x, 0x%x)"...
0x18001aaef  mov     edx, 4
0x18001aaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaf9  jmp     loc_18001ACC4
0x18001aafe  lea     rax, [rsp+348h+var_248]
0x18001ab06  mov     [rsp+348h+var_2E8], rax
0x18001ab0b  mov     [rsp+348h+var_2A0], rsi
0x18001ab13  xor     edx, edx; struct _IMAGE_NT_HEADERS64 *
0x18001ab15  mov     rcx, rax; void *
0x18001ab18  call    ?GenImageNtHeader@@YAPEAU_IMAGE_NT_HEADERS64@@PEAXPEAU1@@Z; GenImageNtHeader(void *,_IMAGE_NT_HEADERS64 *)
0x18001ab1d  mov     r12, rax
0x18001ab20  test    rax, rax
0x18001ab23  jnz     short loc_18001AB4F
0x18001ab25  mov     ebx, 80070482h
0x18001ab2a  mov     rcx, [r14+28h]
0x18001ab2e  mov     rax, [rcx]
0x18001ab31  mov     r9, [r13+8]
0x18001ab35  lea     r8, aGengetimagesec_0; "GenGetImageSections.GenImageNtHeader(0x"...
0x18001ab3c  lea     edx, [r12+4]
0x18001ab41  mov     rax, [rax+8]
0x18001ab45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab4a  jmp     loc_18001ACAB
0x18001ab4f  mov     ebx, edi
0x18001ab51  movzx   r15d, word ptr [rax+14h]
0x18001ab56  add     r15, 18h
0x18001ab5a  add     r15, r12
0x18001ab5d  cmp     [rsp+348h+var_308], rdi
0x18001ab62  jz      short loc_18001ABD0
0x18001ab64  mov     esi, edi
0x18001ab66  mov     [rsp+348h+var_2E0], edi
0x18001ab6a  movzx   eax, word ptr [r12+6]
0x18001ab70  cmp     esi, eax
0x18001ab72  jnb     short loc_18001ABAC
0x18001ab74  mov     eax, esi
0x18001ab76  lea     rcx, [rax+rax*4]
0x18001ab7a  lea     rax, [r15+rcx*8]
0x18001ab7e  mov     [rsp+348h+var_328], rax; struct _IMAGE_SECTION_HEADER *
0x18001ab83  mov     r9d, [rsp+348h+var_2EC]; unsigned int
0x18001ab88  mov     r8, r13; struct _INTERNAL_MODULE *
0x18001ab8b  mov     rdx, [rsp+348h+var_2B8]; struct _INTERNAL_PROCESS *
0x18001ab93  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001ab96  call    ?GenAddImageSection@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_MODULE@@KPEAU_IMAGE_SECTION_HEADER@@@Z; GenAddImageSection(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_MODULE *,ulong,_IMAGE_SECTION_HEADER *)
0x18001ab9b  test    eax, eax
0x18001ab9d  cmovnz  ebx, eax
0x18001aba0  mov     [rsp+348h+var_2D0], ebx
0x18001aba4  inc     esi
0x18001aba6  mov     [rsp+348h+var_2E0], esi
0x18001abaa  jmp     short loc_18001AB6A
0x18001abac  mov     rsi, [rsp+348h+var_2B0]
0x18001abb4  jmp     loc_18001ACAB
0x18001abb9  mov     ebx, eax
0x18001abbb  bts     ebx, 1Ch
0x18001abbf  mov     [rsp+348h+var_2D0], ebx
0x18001abc3  mov     rsi, [rsp+348h+var_2A0]
0x18001abcb  jmp     loc_18001ACAB
0x18001abd0  xorps   xmm0, xmm0
0x18001abd3  xor     eax, eax
0x18001abd5  movups  xmmword ptr [rsp+348h+var_278.Name], xmm0
0x18001abdd  movups  xmmword ptr [rsp+348h+var_278.SizeOfRawData], xmm0
0x18001abe5  mov     qword ptr [rsp+348h+var_278.NumberOfRelocations], rax
0x18001abed  sub     r15, [rsp+348h+var_2E8]
0x18001abf2  add     r15, [r13+8]
0x18001abf6  mov     dword ptr [rsp+348h+var_2E8], edi
0x18001abfa  cmp     di, [r12+6]
0x18001ac00  jnb     loc_18001ACAB
0x18001ac06  mov     rcx, [rsi]
0x18001ac09  mov     rax, [rcx]
0x18001ac0c  mov     dword ptr [rsp+348h+var_328], 28h ; '('
0x18001ac14  lea     r9, [rsp+348h+var_278]
0x18001ac1c  mov     r8, r15
0x18001ac1f  mov     rdx, [r14]
0x18001ac22  mov     rax, [rax+0F0h]
0x18001ac29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac2e  mov     r8d, eax
0x18001ac31  test    eax, eax
0x18001ac33  jz      short loc_18001AC65
0x18001ac35  mov     ebx, eax
0x18001ac37  mov     rcx, [r14+28h]
0x18001ac3b  mov     rdx, [rcx]
0x18001ac3e  mov     rax, [rdx+8]
0x18001ac42  mov     dword ptr [rsp+348h+var_320], ebx
0x18001ac46  mov     [rsp+348h+var_328], 28h ; '('
0x18001ac4f  mov     r9, r15
0x18001ac52  lea     r8, aGengetimagesec; "GenGetImageSections.Section.Read(0x%I64"...
0x18001ac59  mov     edx, 4
0x18001ac5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac63  jmp     short loc_18001AC8F
0x18001ac65  lea     rax, [rsp+348h+var_278]
0x18001ac6d  mov     [rsp+348h+var_328], rax; struct _IMAGE_SECTION_HEADER *
0x18001ac72  mov     r9d, [rsp+348h+var_2EC]; unsigned int
0x18001ac77  mov     r8, r13; struct _INTERNAL_MODULE *
0x18001ac7a  mov     rdx, [rsp+348h+var_2B8]; struct _INTERNAL_PROCESS *
0x18001ac82  mov     rcx, r14; struct _MINIDUMP_STATE *
0x18001ac85  call    ?GenAddImageSection@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_MODULE@@KPEAU_IMAGE_SECTION_HEADER@@@Z; GenAddImageSection(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_MODULE *,ulong,_IMAGE_SECTION_HEADER *)
0x18001ac8a  test    eax, eax
0x18001ac8c  cmovnz  ebx, eax
0x18001ac8f  add     r15, 28h ; '('
0x18001ac93  mov     ecx, dword ptr [rsp+348h+var_2E8]
0x18001ac97  inc     ecx
0x18001ac99  mov     dword ptr [rsp+348h+var_2E8], ecx
0x18001ac9d  movzx   eax, word ptr [r12+6]
0x18001aca3  cmp     ecx, eax
0x18001aca5  jb      loc_18001AC06
0x18001acab  mov     rdx, [rsp+348h+var_308]
0x18001acb0  test    rdx, rdx
0x18001acb3  jz      short loc_18001ACC4
0x18001acb5  mov     rcx, [rsi]
0x18001acb8  mov     r8, [rcx]
0x18001acbb  mov     rax, [r8+68h]
0x18001acbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acc4  mov     eax, ebx
0x18001acc6  mov     rcx, [rsp+348h+var_48]
0x18001acce  xor     rcx, rsp; StackCookie
0x18001acd1  call    __security_check_cookie
0x18001acd6  add     rsp, 310h
0x18001acdd  pop     r15
0x18001acdf  pop     r14
0x18001ace1  pop     r13
0x18001ace3  pop     r12
0x18001ace5  pop     rdi
0x18001ace6  pop     rsi
0x18001ace7  pop     rbx
0x18001ace8  retn
0x18002b25f  push    rbp
0x18002b261  sub     rsp, 40h
0x18002b265  mov     rbp, rdx
0x18002b268  mov     rax, [rcx]
0x18002b26b  mov     edx, [rax]
0x18002b26d  mov     eax, [rbp+48h]
0x18002b270  mov     [rbp+70h], eax
0x18002b273  mov     rax, [rbp+40h]
0x18002b277  mov     [rbp+88h], rax
0x18002b27e  mov     [rbp+0A0h], rcx
0x18002b285  mov     [rbp+50h], edx
0x18002b288  mov     rax, [rbp+0A0h]
0x18002b28f  mov     rcx, [rax]
0x18002b292  mov     [rbp+80h], rcx
0x18002b299  mov     eax, [rbp+50h]
0x18002b29c  cmp     eax, 0C0000006h
0x18002b2a1  jz      short loc_18002B2AD
0x18002b2a3  mov     eax, [rbp+50h]
0x18002b2a6  cmp     eax, 0C0000005h
0x18002b2ab  jnz     short loc_18002B2F5
0x18002b2ad  mov     rax, [rbp+80h]
0x18002b2b4  cmp     qword ptr [rax+20h], 0
0x18002b2b9  jnz     short loc_18002B2F5
0x18002b2bb  mov     rax, [rbp+80h]
0x18002b2c2  mov     rcx, [rax+28h]
0x18002b2c6  mov     rax, [rbp+88h]
0x18002b2cd  cmp     rcx, rax
0x18002b2d0  jb      short loc_18002B2F5
0x18002b2d2  mov     ecx, [rbp+70h]
0x18002b2d5  mov     rdx, [rbp+88h]
0x18002b2dc  add     rdx, rcx
0x18002b2df  mov     rax, [rbp+80h]
0x18002b2e6  cmp     [rax+28h], rdx
0x18002b2ea  jnb     short loc_18002B2F5
0x18002b2ec  mov     dword ptr [rbp+58h], 1
0x18002b2f3  jmp     short loc_18002B2FC
0x18002b2f5  mov     dword ptr [rbp+58h], 0
0x18002b2fc  mov     eax, [rbp+58h]
0x18002b2ff  add     rsp, 40h
0x18002b303  pop     rbp
0x18002b304  retn
```
