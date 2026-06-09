# SString::LoadResourceAndReturnHR(CCompRC *,CCompRC::ResourceCategory,int)

- ea: `0x14001181c`
- end: `0x140011b6a`
- name: `?LoadResourceAndReturnHR@SString@@QEAAJPEAVCCompRC@@W4ResourceCategory@2@H@Z`
- size: `846`
- prototype: `__int64 __fastcall(unsigned int *, unsigned __int16 *, int, UINT)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000e748`

## callees

- `0x14000aedc`
- `0x14000b010`
- `0x14000c51c`
- `0x14000c56c`
- `0x14000c610`
- `0x14000e71c`
- `0x1400102cc`
- `0x14001181c`
- `0x140012450`
- `0x1400124f8`
- `0x140013f30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001194b`
- `KERNEL32!GetLastError` at `0x140011960`
- `KERNEL32!GetLastError` at `0x140011993`
- `KERNEL32!GetLastError` at `0x14001194b`
- `KERNEL32!GetLastError` at `0x140011960`
- `KERNEL32!GetLastError` at `0x140011993`
- `USER32!LoadStringW` at `0x140011930`
- `USER32!LoadStringW` at `0x140011930`

## pseudocode

```c
__int64 __fastcall SString::LoadResourceAndReturnHR(unsigned int *a1, unsigned __int16 *a2, int a3, UINT a4)
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
  int v25; // [rsp+28h] [rbp-80h] BYREF
  HINSTANCE v26; // [rsp+30h] [rbp-78h]
  HINSTANCE hInstance; // [rsp+38h] [rbp-70h] BYREF
  BOOL v28; // [rsp+40h] [rbp-68h]
  void **v29; // [rsp+48h] [rbp-60h] BYREF
  __int64 v30; // [rsp+50h] [rbp-58h]
  __int64 v31; // [rsp+58h] [rbp-50h]
  _QWORD v32[3]; // [rsp+60h] [rbp-48h] BYREF
  HINSTANCE v33[6]; // [rsp+78h] [rbp-30h] BYREF
  unsigned __int16 *v34; // [rsp+B8h] [rbp+10h] BYREF
  int v35; // [rsp+C0h] [rbp+18h]
  UINT uID; // [rsp+C8h] [rbp+20h]

  uID = a4;
  v35 = a3;
  v34 = a2;
  Library = -2147467259;
  if ( !CCompRC::m_dwDefaultInitialized )
  {
    if ( (int)CCompRC::Init((CCompRC *)a1, a2) < 0 )
      return (unsigned int)Library;
    CCompRC::m_dwDefaultInitialized = 1;
  }
  v35 = 0;
  v6 = 0;
  v25 = 0;
  v26 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      v34 = (unsigned __int16 *)&v25;
      if ( *a1 >> ((a1[2] & 1) == 0) == 1 )
        SString::Resize((__int64)a1, 255u, 4, 0);
      while ( 1 )
      {
        v7 = *a1 >> ((a1[2] & 1) == 0);
        v8 = (WCHAR *)*((_QWORD *)a1 + 2);
        if ( qword_1400279F8 )
        {
          if ( !(unsigned int)qword_1400279F8(&v34) )
          {
            Library = -2147418113;
            v9 = v35;
            goto LABEL_31;
          }
          v10 = (unsigned int)v34;
        }
        else
        {
          v10 = -1;
        }
        hInstance = 0;
        Library = CCompRC::GetLibrary((CCompRC *)CCompRC::m_DefaultResourceDll, v10, &hInstance);
        if ( Library >= 0 )
        {
          StringW = LoadStringW(hInstance, uID, v8, v7);
          v9 = StringW;
          if ( StringW > 0 )
          {
            v35 = StringW;
            Library = 0;
            goto LABEL_31;
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
            if ( dword_140027A08 )
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
            goto LABEL_27;
          }
          Library = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            Library = LastError;
        }
        if ( Library != -2147024882 )
          goto LABEL_22;
LABEL_27:
        if ( v8 && v7 )
          *v8 = 0;
        v9 = v35;
LABEL_31:
        if ( Library != -2147024774 )
        {
          if ( Library < 0 )
          {
            SString::Clear((SString *)a1);
LABEL_35:
            if ( Library >= 0 )
            {
              if ( (~(a1[2] >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)a1) )
                SString::ConvertToUnicode((SString *)a1);
              if ( (a1[2] & 0x10) != 0 )
                SBuffer::ReallocateBuffer((const void **)a1, a1[1], 1);
              v14 = (a1[2] & 1) == 0;
              v15 = (void **)*((_QWORD *)a1 + 2);
              v29 = v15;
              LODWORD(v30) = v14;
              v16 = -1;
              do
                ++v16;
              while ( *((_WORD *)v15 + v16) );
              v32[1] = v30;
              v32[2] = v31;
              v32[0] = (char *)v15 + (int)((_DWORD)v16 << v14);
              SString::Truncate((SString *)a1, (const struct SString::Iterator *)v32);
            }
            SString::ConvertToUnicode((SString *)a1);
            a1[2] |= 0x100u;
            goto LABEL_72;
          }
          if ( v9 < (int)((*a1 >> ((a1[2] & 1) == 0)) - 1) )
            goto LABEL_35;
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
            SBuffer::ReallocateBuffer((const void **)a1, v20, 0);
          *a1 = v20;
          if ( (a1[2] & 0x10) != 0 )
            SBuffer::ReallocateBuffer((const void **)a1, a1[1], 1);
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
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &Exception * `RTTI Type Descriptor', (Exception **)v33) )
      {
        Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v25);
        v26 = v33[0];
        throw;
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_ellipsis(0) )
    {
      v30 = 0;
      v29 = &DelegatingException::`vftable';
      v31 = -1;
      v23 = v26;
      hInstance = v26;
      v24 = v26 != 0;
      v28 = v24;
      ((void (__fastcall *)(Exception::HandlerState *, int, bool))Exception::HandlerState::SetupCatch)(
        (Exception::HandlerState *)&v25,
        95,
        v17);
      if ( v24 )
      {
        if ( v23 && !(*(unsigned int (__fastcall **)(HINSTANCE))(*(_QWORD *)v23 + 80LL))(v23) )
          (**(void (__fastcall ***)(HINSTANCE, __int64))v23)(v23, 5);
        v28 = 0;
      }
      DelegatingException::~DelegatingException((DelegatingException *)&v29);
      Library = -2147467259;
      v6 = v25;
      __eh34_try_continuation(0, &loc_140011B28);
    }
  }
LABEL_72:
  if ( (v6 & 2) != 0 && g_fpHandleStackOverflowAfterCatch )
    g_fpHandleStackOverflowAfterCatch();
  return (unsigned int)Library;
}

```

## disassembly

```asm
0x14001181c  mov     rax, rsp
0x14001181f  mov     [rax+8], rbx
0x140011823  mov     [rax+20h], r9d
0x140011827  mov     [rax+18h], r8d
0x14001182b  mov     [rax+10h], rdx
0x14001182f  push    rsi
0x140011830  push    rdi
0x140011831  push    r12
0x140011833  push    r13
0x140011835  push    r15
0x140011837  sub     rsp, 80h
0x14001183e  mov     rbx, rcx
0x140011841  mov     edi, 80004005h
0x140011846  xor     esi, esi
0x140011848  cmp     cs:?m_dwDefaultInitialized@CCompRC@@0JA, esi; long CCompRC::m_dwDefaultInitialized
0x14001184e  jnz     short loc_140011867
0x140011850  call    ?Init@CCompRC@@QEAAJPEAGH@Z; CCompRC::Init(ushort *,int)
0x140011855  test    eax, eax
0x140011857  js      loc_140011B49
0x14001185d  mov     cs:?m_dwDefaultInitialized@CCompRC@@0JA, 1; long CCompRC::m_dwDefaultInitialized
0x140011867  mov     [rsp+0A8h+arg_10], esi
0x14001186e  mov     r13d, esi
0x140011871  mov     [rsp+0A8h+var_80], esi
0x140011875  mov     [rsp+0A8h+var_78], rsi
0x14001187a  lea     rax, [rsp+0A8h+var_80]
0x14001187f  mov     [rsp+0A8h+arg_8], rax
0x140011887  mov     ecx, [rbx+8]
0x14001188a  not     ecx
0x14001188c  and     ecx, 1
0x14001188f  mov     eax, [rbx]
0x140011891  shr     eax, cl
0x140011893  cmp     eax, 1
0x140011896  jnz     short loc_1400118AC
0x140011898  xor     r9d, r9d
0x14001189b  mov     edx, 0FFh
0x1400118a0  lea     r8d, [rax+3]
0x1400118a4  mov     rcx, rbx
0x1400118a7  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x1400118ac  mov     ecx, [rbx+8]
0x1400118af  not     ecx
0x1400118b1  and     ecx, 1
0x1400118b4  mov     r15d, [rbx]
0x1400118b7  shr     r15d, cl
0x1400118ba  mov     r12, [rbx+10h]
0x1400118be  mov     rax, cs:qword_1400279F8
0x1400118c5  test    rax, rax
0x1400118c8  jz      short loc_1400118FB
0x1400118ca  lea     rcx, [rsp+0A8h+arg_8]
0x1400118d2  call    cs:__guard_dispatch_icall_fptr
0x1400118d8  test    eax, eax
0x1400118da  jnz     short loc_1400118F2
0x1400118dc  mov     edi, 8000FFFFh
0x1400118e1  mov     [rsp+0A8h+var_84], edi
0x1400118e5  mov     r8d, [rsp+0A8h+arg_10]
0x1400118ed  jmp     loc_1400119D5
0x1400118f2  mov     edx, dword ptr [rsp+0A8h+arg_8]
0x1400118f9  jmp     short loc_1400118FE
0x1400118fb  or      edx, 0FFFFFFFFh; unsigned int
0x1400118fe  mov     [rsp+0A8h+hInstance], rsi
0x140011903  lea     r8, [rsp+0A8h+hInstance]; HINSTANCE *
0x140011908  lea     rcx, ?m_DefaultResourceDll@CCompRC@@0V1@A; this
0x14001190f  call    ?GetLibrary@CCompRC@@AEAAJKPEAPEAUHINSTANCE__@@@Z; CCompRC::GetLibrary(ulong,HINSTANCE__ * *)
0x140011914  mov     edi, eax
0x140011916  mov     [rsp+0A8h+var_88], eax
0x14001191a  test    eax, eax
0x14001191c  js      short loc_140011983
0x14001191e  mov     r9d, r15d; cchBufferMax
0x140011921  mov     r8, r12; lpBuffer
0x140011924  mov     edx, [rsp+0A8h+uID]; uID
0x14001192b  mov     rcx, [rsp+0A8h+hInstance]; hInstance
0x140011930  call    cs:__imp_LoadStringW
0x140011936  mov     r8d, eax
0x140011939  test    eax, eax
0x14001193b  jle     short loc_14001194B
0x14001193d  mov     [rsp+0A8h+arg_10], eax
0x140011944  mov     edi, esi
0x140011946  jmp     loc_1400119D1
0x14001194b  call    cs:__imp_GetLastError
0x140011951  test    eax, eax
0x140011953  jnz     short loc_140011960
0x140011955  mov     edi, 80070490h
0x14001195a  mov     [rsp+0A8h+var_88], edi
0x14001195e  jmp     short loc_14001198B
0x140011960  call    cs:__imp_GetLastError
0x140011966  test    eax, eax
0x140011968  jnz     short loc_140011971
0x14001196a  mov     edi, 80004005h
0x14001196f  jmp     short loc_14001195A
0x140011971  movzx   edi, ax
0x140011974  or      edi, 80070000h
0x14001197a  test    eax, eax
0x14001197c  cmovle  edi, eax
0x14001197f  mov     [rsp+0A8h+var_88], edi
0x140011983  cmp     edi, 8007000Eh
0x140011989  jz      short loc_1400119BA
0x14001198b  cmp     cs:dword_140027A08, esi
0x140011991  jz      short loc_1400119BA
0x140011993  call    cs:__imp_GetLastError
0x140011999  test    eax, eax
0x14001199b  jnz     short loc_1400119A8
0x14001199d  mov     edi, 80004005h
0x1400119a2  mov     [rsp+0A8h+var_88], edi
0x1400119a6  jmp     short loc_1400119BA
0x1400119a8  movzx   edi, ax
0x1400119ab  or      edi, 80070000h
0x1400119b1  test    eax, eax
0x1400119b3  cmovle  edi, eax
0x1400119b6  mov     [rsp+0A8h+var_88], edi
0x1400119ba  test    r12, r12
0x1400119bd  jz      short loc_1400119C9
0x1400119bf  test    r15d, r15d
0x1400119c2  jz      short loc_1400119C9
0x1400119c4  mov     [r12], si
0x1400119c9  mov     r8d, [rsp+0A8h+arg_10]
0x1400119d1  mov     [rsp+0A8h+var_84], edi
0x1400119d5  cmp     edi, 8007007Ah
0x1400119db  jz      loc_140011AA9
0x1400119e1  test    edi, edi
0x1400119e3  jns     short loc_1400119EF
0x1400119e5  mov     rcx, rbx; this
0x1400119e8  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x1400119ed  jmp     short loc_140011A06
0x1400119ef  mov     ecx, [rbx+8]
0x1400119f2  not     ecx
0x1400119f4  and     ecx, 1
0x1400119f7  mov     edx, [rbx]
0x1400119f9  shr     edx, cl
0x1400119fb  dec     edx
0x1400119fd  cmp     r8d, edx
0x140011a00  jge     loc_140011AA9
0x140011a06  test    edi, edi
0x140011a08  js      loc_140011A97
0x140011a0e  mov     eax, [rbx+8]
0x140011a11  shr     eax, 1
0x140011a13  not     eax
0x140011a15  test    al, 1
0x140011a17  jz      short loc_140011A1B
0x140011a19  jmp     short loc_140011A2F
0x140011a1b  mov     rcx, rbx; this
0x140011a1e  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x140011a23  test    eax, eax
0x140011a25  jnz     short loc_140011A19
0x140011a27  mov     rcx, rbx; this
0x140011a2a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140011a2f  test    byte ptr [rbx+8], 10h
0x140011a33  jz      short loc_140011A46
0x140011a35  mov     r8d, 1
0x140011a3b  mov     edx, [rbx+4]
0x140011a3e  mov     rcx, rbx
0x140011a41  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140011a46  mov     ecx, [rbx+8]
0x140011a49  not     ecx
0x140011a4b  and     ecx, 1
0x140011a4e  mov     rdx, [rbx+10h]
0x140011a52  mov     qword ptr [rsp+0A8h+var_60], rdx
0x140011a57  mov     dword ptr [rsp+0A8h+var_60+8], ecx
0x140011a5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011a5f  inc     rax
0x140011a62  cmp     [rdx+rax*2], si
0x140011a66  jnz     short loc_140011A5F
0x140011a68  movups  xmm0, [rsp+0A8h+var_60]
0x140011a6d  movups  [rsp+0A8h+var_48], xmm0
0x140011a72  movsd   xmm1, [rsp+0A8h+var_50]
0x140011a78  movsd   [rsp+0A8h+var_38], xmm1
0x140011a7e  shl     eax, cl
0x140011a80  cdqe
0x140011a82  add     rax, rdx
0x140011a85  mov     qword ptr [rsp+0A8h+var_48], rax
0x140011a8a  lea     rdx, [rsp+0A8h+var_48]; struct SString::Iterator *
0x140011a8f  mov     rcx, rbx; this
0x140011a92  call    ?Truncate@SString@@QEAAXAEBVIterator@1@@Z; SString::Truncate(SString::Iterator const &)
0x140011a97  mov     rcx, rbx; this
0x140011a9a  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140011a9f  bts     dword ptr [rbx+8], 8
0x140011aa4  jmp     loc_140011B31
0x140011aa9  add     r8d, r8d
0x140011aac  jnz     short loc_140011AB8
0x140011aae  mov     rcx, rbx; this
0x140011ab1  call    ?Clear@SString@@QEAAXXZ; SString::Clear(void)
0x140011ab6  jmp     short loc_140011B23
0x140011ab8  and     dword ptr [rbx+8], 0FFFFFFF8h
0x140011abc  mov     edx, [rbx+8]
0x140011abf  or      edx, 4
0x140011ac2  mov     [rbx+8], edx
0x140011ac5  mov     ecx, edx
0x140011ac7  not     ecx
0x140011ac9  and     ecx, 1
0x140011acc  lea     edi, [r8+1]
0x140011ad0  shl     edi, cl
0x140011ad2  cmp     edi, r8d
0x140011ad5  jb      loc_140011B63
0x140011adb  btr     edx, 8
0x140011adf  mov     [rbx+8], edx
0x140011ae2  cmp     edi, [rbx+4]
0x140011ae5  jbe     short loc_140011AF4
0x140011ae7  xor     r8d, r8d
0x140011aea  mov     edx, edi
0x140011aec  mov     rcx, rbx
0x140011aef  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140011af4  mov     [rbx], edi
0x140011af6  test    byte ptr [rbx+8], 10h
0x140011afa  jz      short loc_140011B0D
0x140011afc  mov     r8d, 1
0x140011b02  mov     edx, [rbx+4]
0x140011b05  mov     rcx, rbx
0x140011b08  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x140011b0d  mov     eax, [rbx]
0x140011b0f  add     rax, [rbx+10h]
0x140011b13  test    byte ptr [rbx+8], 1
0x140011b17  jz      short loc_140011B1F
0x140011b19  mov     [rax-1], sil
0x140011b1d  jmp     short loc_140011B23
0x140011b1f  mov     [rax-2], si
0x140011b23  jmp     loc_1400118AC
0x140011b28  mov     edi, [rsp+0A8h+var_84]
0x140011b2c  mov     r13d, [rsp+0A8h+var_80]
0x140011b31  test    r13b, 2
0x140011b35  jz      short loc_140011B49
0x140011b37  mov     rax, cs:?g_fpHandleStackOverflowAfterCatch@@3P6AXXZEA; void (*g_fpHandleStackOverflowAfterCatch)(void)
0x140011b3e  test    rax, rax
0x140011b41  jz      short loc_140011B49
0x140011b43  call    cs:__guard_dispatch_icall_fptr
0x140011b49  mov     eax, edi
0x140011b4b  mov     rbx, [rsp+0A8h+arg_0]
0x140011b53  add     rsp, 80h
0x140011b5a  pop     r15
0x140011b5c  pop     r13
0x140011b5e  pop     r12
0x140011b60  pop     rdi
0x140011b61  pop     rsi
0x140011b62  retn
0x140011b63  call    ?ThrowOutOfMemory@@YAXXZ; ThrowOutOfMemory(void)
```
