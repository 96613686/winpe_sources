# DfCreateDocfile

- ea: `0x180039a04`
- end: `0x180039c8b`
- name: `DfCreateDocfile`
- size: `647`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, int, struct IStorage **)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033544`
- `0x1800399d0`

## callees

- `0x180015258`
- `0x18001c2ac`
- `0x18001eef0`
- `0x18001faf0`
- `0x180023e70`
- `0x180026bc4`
- `0x180033810`
- `0x180039a04`
- `0x18004e6e0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180039baf`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180039baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039b70`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180039b66`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180039b66`

## pseudocode

```c
__int64 __fastcall DfCreateDocfile(
        unsigned __int16 *a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        struct IStorage **ReservedForOle)
{
  struct IStorage **v6; // r13
  struct CExposedDocFile *v10; // r14
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  int v13; // ebx
  int SimpDocfile; // eax
  unsigned int v15; // eax
  unsigned int v16; // esi
  int v17; // r12d
  DWORD LastError; // eax
  struct IMalloc *v20; // [rsp+38h] [rbp-60h]
  struct CExposedDocFile *v21[11]; // [rsp+40h] [rbp-58h] BYREF

  v6 = ReservedForOle;
  v21[0] = 0;
  v10 = 0;
  if ( ReservedForOle )
  {
    *ReservedForOle = 0;
    if ( a1 )
    {
      if ( !(unsigned int)IsValidReadPtrIn(a1, 0x104u) )
      {
LABEL_7:
        v13 = -2147286788;
        goto LABEL_42;
      }
      v12 = a1;
      while ( *v12 )
      {
        ++v12;
        if ( !--v11 )
          goto LABEL_7;
      }
    }
    if ( (a2 & 0x8000000) != 0 )
    {
      if ( a4 > 0x200 )
      {
LABEL_10:
        v13 = -2147286953;
        goto LABEL_42;
      }
      SimpDocfile = DfCreateSimpDocfile(a1, a2, a3, v6);
      goto LABEL_12;
    }
    v13 = VerifyPerms(a2, 1);
    if ( v13 >= 0 )
    {
      if ( (a2 & 0x4020000) != 67239936 && (a2 & 3) != 0 )
      {
        v15 = ModeToDFlags(a2);
        v16 = v15 | 4;
        if ( (a2 & 0x30000) != 0x30000 )
          v16 = v15;
        if ( a4 <= 0x200 )
        {
          v17 = 0;
          if ( a4 && a4 != 512 )
            goto LABEL_10;
        }
        else
        {
          switch ( a4 )
          {
            case 0x1000u:
              v17 = 49152;
              break;
            case 0x2000u:
              v17 = 53248;
              break;
            case 0x4000u:
              v17 = 57344;
              break;
            case 0x8000u:
              v17 = 61440;
              break;
            default:
              goto LABEL_10;
          }
          v16 |= 0x80000u;
        }
        if ( (a2 & 0x1000) != 0
          && (a5 & 0x4000) == 0
          && (int)CNtfsStorage::IsNffAppropriate(a1) >= 0
          && !DeleteFileW(a1) )
        {
          LastError = GetLastError();
          if ( LastError - 2 > 1 )
          {
            SimpDocfile = Win32ErrorToScode(LastError);
LABEL_12:
            v13 = SimpDocfile;
            goto LABEL_42;
          }
        }
        ReservedForOle = (struct IStorage **)NtCurrentTeb()->ReservedForOle;
        if ( ReservedForOle || (v13 = InternalTlsAllocData(&ReservedForOle), v13 >= 0) )
        {
          Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(v21);
          v13 = DfFromName(
                  a1,
                  v16,
                  v17
                | (a5 >> 4) & 0x400
                | ((a2 & 0x1000) != 0 ? 2 : 0)
                | ((a2 & 0x20000 | ((a5 & 0x20000000 | ((a2 & 0x4000000 | 0x1000000) >> 2)) >> 3)) >> 17),
                  0,
                  v21,
                  0,
                  a3,
                  v20);
          if ( v13 < 0 )
            v10 = v21[0];
          else
            *v6 = (struct IStorage *)v21[0];
        }
      }
      else
      {
        v13 = -2147286785;
      }
    }
  }
  else
  {
    v13 = -2147287031;
  }
LABEL_42:
  if ( v10 )
    (*(void (__fastcall **)(struct CExposedDocFile *))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180039a04  mov     [rsp+arg_10], r8
0x180039a09  push    rbx
0x180039a0a  push    rbp
0x180039a0b  push    rsi
0x180039a0c  push    rdi
0x180039a0d  push    r12
0x180039a0f  push    r13
0x180039a11  push    r14
0x180039a13  push    r15
0x180039a15  sub     rsp, 58h
0x180039a19  mov     r13, [rsp+98h+arg_28]
0x180039a21  xor     ebx, ebx
0x180039a23  mov     [rsp+98h+var_58], rbx
0x180039a28  mov     edi, r9d
0x180039a2b  mov     ebp, edx
0x180039a2d  mov     r15, rcx
0x180039a30  mov     r14d, ebx
0x180039a33  test    r13, r13
0x180039a36  jz      loc_180039C5F
0x180039a3c  mov     [r13+0], rbx
0x180039a40  test    rcx, rcx
0x180039a43  jz      short loc_180039A6F
0x180039a45  mov     edx, 104h; unsigned __int64
0x180039a4a  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x180039a4f  test    eax, eax
0x180039a51  jz      short loc_180039A65
0x180039a53  mov     rax, rcx
0x180039a56  cmp     [rax], bx
0x180039a59  jz      short loc_180039A6F
0x180039a5b  add     rax, 2
0x180039a5f  sub     rdx, 1
0x180039a63  jnz     short loc_180039A56
0x180039a65  mov     ebx, 800300FCh
0x180039a6a  jmp     loc_180039C64
0x180039a6f  bt      ebp, 1Bh
0x180039a73  jnb     short loc_180039A99
0x180039a75  mov     eax, 200h
0x180039a7a  cmp     edi, eax
0x180039a7c  jbe     short loc_180039A88
0x180039a7e  mov     ebx, 80030057h
0x180039a83  jmp     loc_180039C64
0x180039a88  mov     r9, r13; struct IStorage **
0x180039a8b  mov     edx, ebp; unsigned int
0x180039a8d  call    ?DfCreateSimpDocfile@@YAJPEBGKPEAXPEAPEAUIStorage@@@Z; DfCreateSimpDocfile(ushort const *,ulong,void *,IStorage * *)
0x180039a92  mov     ebx, eax
0x180039a94  jmp     loc_180039C64
0x180039a99  mov     edx, 1; int
0x180039a9e  mov     ecx, ebp; unsigned int
0x180039aa0  call    ?VerifyPerms@@YAJKH@Z; VerifyPerms(ulong,int)
0x180039aa5  mov     ebx, eax
0x180039aa7  test    eax, eax
0x180039aa9  js      loc_180039C64
0x180039aaf  mov     ecx, 4020000h
0x180039ab4  mov     eax, ebp
0x180039ab6  and     eax, ecx
0x180039ab8  cmp     eax, ecx
0x180039aba  setnz   cl
0x180039abd  test    bpl, 3
0x180039ac1  setnz   al
0x180039ac4  test    al, cl
0x180039ac6  jz      loc_180039C58
0x180039acc  mov     ecx, ebp; unsigned int
0x180039ace  call    ?ModeToDFlags@@YAKK@Z; ModeToDFlags(ulong)
0x180039ad3  mov     edx, 30000h
0x180039ad8  mov     esi, eax
0x180039ada  or      esi, 4
0x180039add  mov     ecx, ebp
0x180039adf  and     ecx, edx
0x180039ae1  cmp     ecx, edx
0x180039ae3  mov     ecx, 1000h
0x180039ae8  mov     edx, 4000h
0x180039aed  cmovnz  esi, eax
0x180039af0  mov     eax, 200h
0x180039af5  cmp     edi, eax
0x180039af7  jbe     short loc_180039B39
0x180039af9  cmp     edi, ecx
0x180039afb  jz      short loc_180039B2D
0x180039afd  cmp     edi, 2000h
0x180039b03  jz      short loc_180039B25
0x180039b05  cmp     edi, edx
0x180039b07  jz      short loc_180039B1D
0x180039b09  cmp     edi, 8000h
0x180039b0f  jnz     loc_180039A7E
0x180039b15  mov     r12d, 0F000h
0x180039b1b  jmp     short loc_180039B33
0x180039b1d  mov     r12d, 0E000h
0x180039b23  jmp     short loc_180039B33
0x180039b25  mov     r12d, 0D000h
0x180039b2b  jmp     short loc_180039B33
0x180039b2d  mov     r12d, 0C000h
0x180039b33  bts     esi, 13h
0x180039b37  jmp     short loc_180039B48
0x180039b39  xor     r12d, r12d
0x180039b3c  test    edi, edi
0x180039b3e  jz      short loc_180039B48
0x180039b40  cmp     edi, eax
0x180039b42  jnz     loc_180039A7E
0x180039b48  mov     edi, ebp
0x180039b4a  and     edi, ecx
0x180039b4c  jz      short loc_180039B8A
0x180039b4e  test    [rsp+98h+arg_20], edx
0x180039b55  jnz     short loc_180039B8A
0x180039b57  mov     rcx, r15; unsigned __int16 *
0x180039b5a  call    ?IsNffAppropriate@CNtfsStorage@@SAJPEBG@Z; CNtfsStorage::IsNffAppropriate(ushort const *)
0x180039b5f  test    eax, eax
0x180039b61  js      short loc_180039B8A
0x180039b63  mov     rcx, r15; lpFileName
0x180039b66  call    cs:__imp_DeleteFileW
0x180039b6c  test    eax, eax
0x180039b6e  jnz     short loc_180039B8A
0x180039b70  call    cs:__imp_GetLastError
0x180039b76  lea     ecx, [rax-2]
0x180039b79  cmp     ecx, 1
0x180039b7c  jbe     short loc_180039B8A
0x180039b7e  mov     ecx, eax; unsigned int
0x180039b80  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x180039b85  jmp     loc_180039A92
0x180039b8a  mov     rax, gs:30h
0x180039b93  mov     rcx, [rax+1758h]
0x180039b9a  mov     [rsp+98h+arg_28], rcx
0x180039ba2  test    rcx, rcx
0x180039ba5  jnz     short loc_180039BBF
0x180039ba7  lea     rcx, [rsp+98h+arg_28]
0x180039baf  call    cs:__imp_InternalTlsAllocData
0x180039bb5  mov     ebx, eax
0x180039bb7  test    eax, eax
0x180039bb9  js      loc_180039C64
0x180039bbf  lea     rcx, [rsp+98h+var_58]
0x180039bc4  call    ?InternalRelease@?$ComPtr@VCExposedDocFile@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CExposedDocFile>::InternalRelease(void)
0x180039bc9  mov     ecx, [rsp+98h+arg_20]
0x180039bd0  mov     r8d, ebp
0x180039bd3  and     r8d, 4000000h
0x180039bda  mov     eax, ecx
0x180039bdc  bts     r8d, 18h
0x180039be1  and     eax, 20000000h
0x180039be6  shr     r8d, 2
0x180039bea  and     ebp, 20000h
0x180039bf0  or      r8d, eax
0x180039bf3  mov     edx, esi; unsigned int
0x180039bf5  shr     r8d, 3
0x180039bf9  or      r8d, ebp
0x180039bfc  shr     r8d, 11h
0x180039c00  neg     edi
0x180039c02  sbb     eax, eax
0x180039c04  shr     ecx, 4
0x180039c07  and     eax, 2
0x180039c0a  and     ecx, 400h
0x180039c10  or      r8d, eax
0x180039c13  xor     r9d, r9d; unsigned __int16 **
0x180039c16  mov     rax, [rsp+98h+arg_10]
0x180039c1e  or      r8d, ecx
0x180039c21  mov     [rsp+98h+var_68], rax; void *
0x180039c26  or      r8d, r12d; unsigned int
0x180039c29  lea     rax, [rsp+98h+var_58]
0x180039c2e  mov     [rsp+98h+var_70], r14; unsigned int *
0x180039c33  mov     rcx, r15; unsigned __int16 *
0x180039c36  mov     [rsp+98h+var_78], rax; struct CExposedDocFile **
0x180039c3b  call    ?DfFromName@@YAJPEBGKKPEAPEAGPEAPEAVCExposedDocFile@@PEAKPEAXPEAU_GUID@@@Z; DfFromName(ushort const *,ulong,ulong,ushort * *,CExposedDocFile * *,ulong *,void *,_GUID *)
0x180039c40  mov     ebx, eax
0x180039c42  test    eax, eax
0x180039c44  js      short loc_180039C51
0x180039c46  mov     rax, [rsp+98h+var_58]
0x180039c4b  mov     [r13+0], rax
0x180039c4f  jmp     short loc_180039C64
0x180039c51  mov     r14, [rsp+98h+var_58]
0x180039c56  jmp     short loc_180039C64
0x180039c58  mov     ebx, 800300FFh
0x180039c5d  jmp     short loc_180039C64
0x180039c5f  mov     ebx, 80030009h
0x180039c64  test    r14, r14
0x180039c67  jz      short loc_180039C78
0x180039c69  mov     rax, [r14]
0x180039c6c  mov     rcx, r14
0x180039c6f  mov     rax, [rax+10h]
0x180039c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c78  mov     eax, ebx
0x180039c7a  add     rsp, 58h
0x180039c7e  pop     r15
0x180039c80  pop     r14
0x180039c82  pop     r13
0x180039c84  pop     r12
0x180039c86  pop     rdi
0x180039c87  pop     rsi
0x180039c88  pop     rbp
0x180039c89  pop     rbx
0x180039c8a  retn
```
