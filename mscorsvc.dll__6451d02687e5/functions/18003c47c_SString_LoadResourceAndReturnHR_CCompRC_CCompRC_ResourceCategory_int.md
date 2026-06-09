# SString::LoadResourceAndReturnHR(CCompRC *,CCompRC::ResourceCategory,int)

- ea: `0x18003c47c`
- end: `0x18003c7eb`
- name: `?LoadResourceAndReturnHR@SString@@QEAAJPEAVCCompRC@@W4ResourceCategory@2@H@Z`
- size: `879`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035228`
- `0x18003aad8`

## callees

- `0x180030c50`
- `0x180030d84`
- `0x180032ef4`
- `0x180032f44`
- `0x180032fe8`
- `0x18003303c`
- `0x1800351fc`
- `0x18003c47c`
- `0x18003cdac`
- `0x18003ce54`
- `0x18003f280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003c5a2`
- `KERNEL32!GetLastError` at `0x18003c5b7`
- `KERNEL32!GetLastError` at `0x18003c614`
- `KERNEL32!GetLastError` at `0x18003c5a2`
- `KERNEL32!GetLastError` at `0x18003c5b7`
- `KERNEL32!GetLastError` at `0x18003c614`
- `USER32!LoadStringW` at `0x18003c587`
- `USER32!LoadStringW` at `0x18003c587`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SString::LoadResourceAndReturnHR(unsigned int *a1, unsigned __int16 *a2, unsigned int a3, UINT a4)
{
  signed int Library; // edi
  char v6; // r13
  int v7; // r15d
  WCHAR *v8; // r12
  int v9; // r8d
  unsigned int v10; // edx
  int StringW; // eax
  signed int LastError; // eax
  signed int v13; // eax
  int v14; // ecx
  void **v15; // rdx
  __int64 v16; // rax
  bool v17; // r8
  unsigned int v18; // r8d
  int v19; // edx
  unsigned int v20; // edi
  __int64 v21; // rax
  HINSTANCE v23; // rdi
  BOOL v24; // ebx
  unsigned int v25; // [rsp+28h] [rbp-90h] BYREF
  HINSTANCE hInstance; // [rsp+30h] [rbp-88h] BYREF
  BOOL v27; // [rsp+38h] [rbp-80h]
  int v28; // [rsp+40h] [rbp-78h] BYREF
  HINSTANCE v29; // [rsp+48h] [rbp-70h]
  void **v30; // [rsp+50h] [rbp-68h] BYREF
  __int64 v31; // [rsp+58h] [rbp-60h]
  __int64 v32; // [rsp+60h] [rbp-58h]
  _QWORD v33[3]; // [rsp+68h] [rbp-50h] BYREF
  HINSTANCE v34; // [rsp+80h] [rbp-38h] BYREF
  int v35; // [rsp+C8h] [rbp+10h]

  Library = -2147467259;
  if ( !CCompRC::m_dwDefaultInitialized )
  {
    if ( (int)CCompRC::Init((CCompRC *)a1, a2) < 0 )
      return (unsigned int)Library;
    CCompRC::m_dwDefaultInitialized = 1;
  }
  v35 = 0;
  v6 = 0;
  v28 = 0;
  v29 = 0;
  try
  {
    try
    {
      hInstance = (HINSTANCE)&v28;
      if ( *a1 >> ((a1[2] & 1) == 0) == 1 )
        SString::Resize(a1, 255, 4);
      while ( 1 )
      {
        v7 = *a1 >> ((a1[2] & 1) == 0);
        v8 = (WCHAR *)*((_QWORD *)a1 + 2);
        if ( qword_18006FEC8 )
        {
          if ( !(unsigned int)qword_18006FEC8(&v25) )
          {
            Library = -2147418113;
            v9 = v35;
            goto LABEL_34;
          }
          v10 = v25;
        }
        else
        {
          v10 = -1;
        }
        hInstance = 0;
        Library = CCompRC::GetLibrary((CCompRC *)CCompRC::m_DefaultResourceDll, v10, &hInstance);
        if ( Library >= 0 )
        {
          StringW = LoadStringW(hInstance, a4, v8, v7);
          v9 = StringW;
          if ( StringW > 0 )
          {
            v35 = StringW;
            Library = 0;
            goto LABEL_34;
          }
          if ( !GetLastError() )
          {
            Library = -2147023728;
            goto LABEL_22;
          }
          LastError = GetLastError();
          if ( !LastError )
          {
            Library = -2147467259;
LABEL_22:
            if ( dword_18006FED8 )
            {
              if ( a3 < 4 )
              {
                v13 = GetLastError();
                if ( v13 )
                {
                  Library = (unsigned __int16)v13 | 0x80070000;
                  if ( v13 <= 0 )
                    Library = v13;
                }
                else
                {
                  Library = -2147467259;
                }
              }
              else if ( a3 == 4 )
              {
                Library = -2147467259;
              }
            }
            goto LABEL_30;
          }
          Library = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            Library = LastError;
        }
        if ( Library != -2147024882 )
          goto LABEL_22;
LABEL_30:
        if ( v8 && v7 )
          *v8 = 0;
        v9 = v35;
LABEL_34:
        if ( Library != -2147024774 )
        {
          if ( Library < 0 )
          {
            SString::Clear((SString *)a1);
LABEL_38:
            if ( Library >= 0 )
            {
              if ( (~(a1[2] >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)a1) )
                SString::ConvertToUnicode((SString *)a1);
              if ( (a1[2] & 0x10) != 0 )
                SBuffer::ReallocateBuffer(a1, a1[1], 1);
              v14 = (a1[2] & 1) == 0;
              v15 = (void **)*((_QWORD *)a1 + 2);
              v30 = v15;
              LODWORD(v31) = v14;
              v16 = -1;
              do
                ++v16;
              while ( *((_WORD *)v15 + v16) );
              v33[1] = v31;
              v33[2] = v32;
              v33[0] = (char *)v15 + (int)((_DWORD)v16 << v14);
              SString::Truncate((SString *)a1, (const struct SString::Iterator *)v33);
            }
            SString::ConvertToUnicode((SString *)a1);
            a1[2] |= 0x100u;
            goto LABEL_75;
          }
          if ( v9 < (int)((*a1 >> ((a1[2] & 1) == 0)) - 1) )
            goto LABEL_38;
        }
        v18 = 2 * v9;
        if ( v18 )
        {
          a1[2] &= 0xFFFFFFF8;
          v19 = a1[2] | 4;
          a1[2] = v19;
          v20 = (v18 + 1) << ((v19 & 1) == 0);
          if ( v20 < v18 )
            ThrowOutOfMemory();
          a1[2] = v19 & 0xFFFFFEFF;
          if ( v20 > a1[1] )
            SBuffer::ReallocateBuffer(a1, v20, 0);
          *a1 = v20;
          if ( (a1[2] & 0x10) != 0 )
            SBuffer::ReallocateBuffer(a1, a1[1], 1);
          v21 = *((_QWORD *)a1 + 2) + *a1;
          if ( (a1[2] & 1) != 0 )
            *(_BYTE *)(v21 - 1) = 0;
          else
            *(_WORD *)(v21 - 2) = 0;
        }
        else
        {
          SString::Clear((SString *)a1);
        }
      }
    }
    catch ( Exception *v34 )
    {
      Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v28);
      v29 = v34;
      throw;
    }
  }
  catch ( ... )
  {
    v31 = 0;
    v30 = &DelegatingException::`vftable';
    v32 = -1;
    v23 = v29;
    hInstance = v29;
    v24 = v29 != 0;
    v27 = v24;
    Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v28, 95, v17);
    if ( v24 )
    {
      if ( v23 )
      {
        if ( !(*(unsigned int (__fastcall **)(HINSTANCE))(*(_QWORD *)v23 + 80LL))(v23) )
          (**(void (__fastcall ***)(HINSTANCE, __int64))v23)(v23, 5);
      }
      v27 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)&v30);
    Library = -2147467259;
    v6 = v28;
  }
LABEL_75:
  if ( (v6 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
    g_fpHandleStackOverflowAfterCatch();
  return (unsigned int)Library;
}

```

## disassembly

```asm
0x18003c47c  mov     rax, rsp
0x18003c47f  mov     [rax+8], rbx
0x18003c483  mov     [rax+20h], r9d
0x18003c487  mov     [rax+18h], r8d
0x18003c48b  mov     [rax+10h], rdx
0x18003c48f  push    rsi
0x18003c490  push    rdi
0x18003c491  push    r12
0x18003c493  push    r13
0x18003c495  push    r15
0x18003c497  sub     rsp, 90h
0x18003c49e  mov     rbx, rcx
0x18003c4a1  mov     edi, 80004005h
0x18003c4a6  xor     esi, esi
0x18003c4a8  cmp     cs:?m_dwDefaultInitialized@CCompRC@@0JA, esi; long CCompRC::m_dwDefaultInitialized
0x18003c4ae  jnz     short loc_18003C4C7
0x18003c4b0  call    ?Init@CCompRC@@QEAAJPEAGH@Z; CCompRC::Init(ushort *,int)
0x18003c4b5  test    eax, eax
0x18003c4b7  js      loc_18003C7CA
0x18003c4bd  mov     cs:?m_dwDefaultInitialized@CCompRC@@0JA, 1; long CCompRC::m_dwDefaultInitialized
0x18003c4c7  mov     [rsp+0B8h+arg_8], esi
0x18003c4ce  mov     r13d, esi
0x18003c4d1  mov     [rsp+0B8h+var_78], esi
0x18003c4d5  mov     [rsp+0B8h+var_70], rsi
0x18003c4da  lea     rax, [rsp+0B8h+var_78]
0x18003c4df  mov     [rsp+0B8h+hInstance], rax
0x18003c4e4  mov     ecx, [rbx+8]
0x18003c4e7  not     ecx
0x18003c4e9  and     ecx, 1
0x18003c4ec  mov     eax, [rbx]
0x18003c4ee  shr     eax, cl
0x18003c4f0  cmp     eax, 1
0x18003c4f3  jnz     short loc_18003C509
0x18003c4f5  xor     r9d, r9d
0x18003c4f8  mov     edx, 0FFh
0x18003c4fd  lea     r8d, [rax+3]
0x18003c501  mov     rcx, rbx
0x18003c504  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x18003c509  mov     ecx, [rbx+8]
0x18003c50c  not     ecx
0x18003c50e  and     ecx, 1
0x18003c511  mov     r15d, [rbx]
0x18003c514  shr     r15d, cl
0x18003c517  mov     r12, [rbx+10h]
0x18003c51b  mov     rax, cs:qword_18006FEC8
0x18003c522  test    rax, rax
0x18003c525  jz      short loc_18003C552
0x18003c527  lea     rcx, [rsp+0B8h+var_90]
0x18003c52c  call    cs:__guard_dispatch_icall_fptr
0x18003c532  test    eax, eax
0x18003c534  jnz     short loc_18003C54C
0x18003c536  mov     edi, 8000FFFFh
0x18003c53b  mov     [rsp+0B8h+var_94], edi
0x18003c53f  mov     r8d, [rsp+0B8h+arg_8]
0x18003c547  jmp     loc_18003C656
0x18003c54c  mov     edx, [rsp+0B8h+var_90]
0x18003c550  jmp     short loc_18003C555
0x18003c552  or      edx, 0FFFFFFFFh; unsigned int
0x18003c555  mov     [rsp+0B8h+hInstance], rsi
0x18003c55a  lea     r8, [rsp+0B8h+hInstance]; HINSTANCE *
0x18003c55f  lea     rcx, ?m_DefaultResourceDll@CCompRC@@0V1@A; this
0x18003c566  call    ?GetLibrary@CCompRC@@AEAAJKPEAPEAUHINSTANCE__@@@Z; CCompRC::GetLibrary(ulong,HINSTANCE__ * *)
0x18003c56b  mov     edi, eax
0x18003c56d  mov     [rsp+0B8h+var_98], eax
0x18003c571  test    eax, eax
0x18003c573  js      short loc_18003C5DA
0x18003c575  mov     r9d, r15d; cchBufferMax
0x18003c578  mov     r8, r12; lpBuffer
0x18003c57b  mov     edx, [rsp+0B8h+uID]; uID
0x18003c582  mov     rcx, [rsp+0B8h+hInstance]; hInstance
0x18003c587  call    cs:__imp_LoadStringW
0x18003c58d  mov     r8d, eax
0x18003c590  test    eax, eax
0x18003c592  jle     short loc_18003C5A2
0x18003c594  mov     [rsp+0B8h+arg_8], eax
0x18003c59b  mov     edi, esi
0x18003c59d  jmp     loc_18003C652
0x18003c5a2  call    cs:__imp_GetLastError
0x18003c5a8  test    eax, eax
0x18003c5aa  jnz     short loc_18003C5B7
0x18003c5ac  mov     edi, 80070490h
0x18003c5b1  mov     [rsp+0B8h+var_98], edi
0x18003c5b5  jmp     short loc_18003C5E2
0x18003c5b7  call    cs:__imp_GetLastError
0x18003c5bd  test    eax, eax
0x18003c5bf  jnz     short loc_18003C5C8
0x18003c5c1  mov     edi, 80004005h
0x18003c5c6  jmp     short loc_18003C5B1
0x18003c5c8  movzx   edi, ax
0x18003c5cb  or      edi, 80070000h
0x18003c5d1  test    eax, eax
0x18003c5d3  cmovle  edi, eax
0x18003c5d6  mov     [rsp+0B8h+var_98], edi
0x18003c5da  cmp     edi, 8007000Eh
0x18003c5e0  jz      short loc_18003C63B
0x18003c5e2  cmp     cs:dword_18006FED8, esi
0x18003c5e8  jz      short loc_18003C63B
0x18003c5ea  mov     ecx, [rsp+0B8h+arg_10]
0x18003c5f1  test    ecx, ecx
0x18003c5f3  jz      short loc_18003C614
0x18003c5f5  sub     ecx, 1
0x18003c5f8  jz      short loc_18003C614
0x18003c5fa  sub     ecx, 1
0x18003c5fd  jz      short loc_18003C614
0x18003c5ff  sub     ecx, 1
0x18003c602  jz      short loc_18003C614
0x18003c604  cmp     ecx, 1
0x18003c607  jnz     short loc_18003C612
0x18003c609  mov     edi, 80004005h
0x18003c60e  mov     [rsp+0B8h+var_98], edi
0x18003c612  jmp     short loc_18003C63B
0x18003c614  call    cs:__imp_GetLastError
0x18003c61a  test    eax, eax
0x18003c61c  jnz     short loc_18003C629
0x18003c61e  mov     edi, 80004005h
0x18003c623  mov     [rsp+0B8h+var_98], edi
0x18003c627  jmp     short loc_18003C63B
0x18003c629  movzx   edi, ax
0x18003c62c  or      edi, 80070000h
0x18003c632  test    eax, eax
0x18003c634  cmovle  edi, eax
0x18003c637  mov     [rsp+0B8h+var_98], edi
0x18003c63b  test    r12, r12
0x18003c63e  jz      short loc_18003C64A
0x18003c640  test    r15d, r15d
0x18003c643  jz      short loc_18003C64A
0x18003c645  mov     [r12], si
0x18003c64a  mov     r8d, [rsp+0B8h+arg_8]
0x18003c652  mov     [rsp+0B8h+var_94], edi
0x18003c656  cmp     edi, 8007007Ah
0x18003c65c  jz      loc_18003C72A
0x18003c662  test    edi, edi
0x18003c664  jns     short loc_18003C670
0x18003c666  mov     rcx, rbx; this
0x18003c669  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x18003c66e  jmp     short loc_18003C687
0x18003c670  mov     ecx, [rbx+8]
0x18003c673  not     ecx
0x18003c675  and     ecx, 1
0x18003c678  mov     edx, [rbx]
0x18003c67a  shr     edx, cl
0x18003c67c  dec     edx
0x18003c67e  cmp     r8d, edx
0x18003c681  jge     loc_18003C72A
0x18003c687  test    edi, edi
0x18003c689  js      loc_18003C718
0x18003c68f  mov     eax, [rbx+8]
0x18003c692  shr     eax, 1
0x18003c694  not     eax
0x18003c696  test    al, 1
0x18003c698  jz      short loc_18003C69C
0x18003c69a  jmp     short loc_18003C6B0
0x18003c69c  mov     rcx, rbx; this
0x18003c69f  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003c6a4  test    eax, eax
0x18003c6a6  jnz     short loc_18003C69A
0x18003c6a8  mov     rcx, rbx; this
0x18003c6ab  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003c6b0  test    byte ptr [rbx+8], 10h
0x18003c6b4  jz      short loc_18003C6C7
0x18003c6b6  mov     r8d, 1
0x18003c6bc  mov     edx, [rbx+4]
0x18003c6bf  mov     rcx, rbx
0x18003c6c2  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003c6c7  mov     ecx, [rbx+8]
0x18003c6ca  not     ecx
0x18003c6cc  and     ecx, 1
0x18003c6cf  mov     rdx, [rbx+10h]
0x18003c6d3  mov     qword ptr [rsp+0B8h+var_68], rdx
0x18003c6d8  mov     dword ptr [rsp+0B8h+var_68+8], ecx
0x18003c6dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c6e0  inc     rax
0x18003c6e3  cmp     [rdx+rax*2], si
0x18003c6e7  jnz     short loc_18003C6E0
0x18003c6e9  movups  xmm0, [rsp+0B8h+var_68]
0x18003c6ee  movups  [rsp+0B8h+var_50], xmm0
0x18003c6f3  movsd   xmm1, [rsp+0B8h+var_58]
0x18003c6f9  movsd   [rsp+0B8h+var_40], xmm1
0x18003c6ff  shl     eax, cl
0x18003c701  cdqe
0x18003c703  add     rax, rdx
0x18003c706  mov     qword ptr [rsp+0B8h+var_50], rax
0x18003c70b  lea     rdx, [rsp+0B8h+var_50]; struct SString::Iterator *
0x18003c710  mov     rcx, rbx; this
0x18003c713  call    ?Truncate@SString@@QEAAXAEBVIterator@1@@Z; SString::Truncate(SString::Iterator const &)
0x18003c718  mov     rcx, rbx; this
0x18003c71b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003c720  bts     dword ptr [rbx+8], 8
0x18003c725  jmp     loc_18003C7B2
0x18003c72a  add     r8d, r8d
0x18003c72d  jnz     short loc_18003C739
0x18003c72f  mov     rcx, rbx; this
0x18003c732  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x18003c737  jmp     short loc_18003C7A4
0x18003c739  and     dword ptr [rbx+8], 0FFFFFFF8h
0x18003c73d  mov     edx, [rbx+8]
0x18003c740  or      edx, 4
0x18003c743  mov     [rbx+8], edx
0x18003c746  mov     ecx, edx
0x18003c748  not     ecx
0x18003c74a  and     ecx, 1
0x18003c74d  lea     edi, [r8+1]
0x18003c751  shl     edi, cl
0x18003c753  cmp     edi, r8d
0x18003c756  jb      loc_18003C7E4
0x18003c75c  btr     edx, 8
0x18003c760  mov     [rbx+8], edx
0x18003c763  cmp     edi, [rbx+4]
0x18003c766  jbe     short loc_18003C775
0x18003c768  xor     r8d, r8d
0x18003c76b  mov     edx, edi
0x18003c76d  mov     rcx, rbx
0x18003c770  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003c775  mov     [rbx], edi
0x18003c777  test    byte ptr [rbx+8], 10h
0x18003c77b  jz      short loc_18003C78E
0x18003c77d  mov     r8d, 1
0x18003c783  mov     edx, [rbx+4]
0x18003c786  mov     rcx, rbx
0x18003c789  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003c78e  mov     eax, [rbx]
0x18003c790  add     rax, [rbx+10h]
0x18003c794  test    byte ptr [rbx+8], 1
0x18003c798  jz      short loc_18003C7A0
0x18003c79a  mov     [rax-1], sil
0x18003c79e  jmp     short loc_18003C7A4
0x18003c7a0  mov     [rax-2], si
0x18003c7a4  jmp     loc_18003C509
0x18003c7a9  mov     edi, [rsp+0B8h+var_94]
0x18003c7ad  mov     r13d, [rsp+0B8h+var_78]
0x18003c7b2  test    r13b, 2
0x18003c7b6  jz      short loc_18003C7CA
0x18003c7b8  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x18003c7bf  test    rax, rax
0x18003c7c2  jz      short loc_18003C7CA
0x18003c7c4  call    cs:__guard_dispatch_icall_fptr
0x18003c7ca  mov     eax, edi
0x18003c7cc  mov     rbx, [rsp+0B8h+arg_0]
0x18003c7d4  add     rsp, 90h
0x18003c7db  pop     r15
0x18003c7dd  pop     r13
0x18003c7df  pop     r12
0x18003c7e1  pop     rdi
0x18003c7e2  pop     rsi
0x18003c7e3  retn
0x18003c7e4  call    ?ThrowOutOfMemory@@YAXXZ; ThrowOutOfMemory(void)
```
