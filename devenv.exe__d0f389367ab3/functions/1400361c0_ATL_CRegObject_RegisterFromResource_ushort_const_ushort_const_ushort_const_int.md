# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1400361c0`
- end: `0x14003639b`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `475`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140033d78`
- `0x14003639c`

## callees

- `0x140001020`
- `0x140033ab0`
- `0x1400344ac`
- `0x1400344d0`
- `0x1400344fc`
- `0x14003601c`
- `0x1400361c0`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140036209`
- `KERNEL32!LoadLibraryExW` at `0x140036225`
- `KERNEL32!LoadLibraryExW` at `0x140036209`
- `KERNEL32!LoadLibraryExW` at `0x140036225`
- `KERNEL32!MultiByteToWideChar` at `0x140036314`
- `KERNEL32!MultiByteToWideChar` at `0x140036314`
- `KERNEL32!FreeLibrary` at `0x14003634e`
- `KERNEL32!FreeLibrary` at `0x14003634e`
- `KERNEL32!SizeofResource` at `0x140036284`
- `KERNEL32!SizeofResource` at `0x140036284`
- `KERNEL32!LoadResource` at `0x14003626b`
- `KERNEL32!LoadResource` at `0x14003626b`
- `KERNEL32!FindResourceW` at `0x14003624d`
- `KERNEL32!FindResourceW` at `0x14003624d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rsi
  unsigned int Error; // ebx
  HRSRC ResourceW; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *Resource; // r14
  DWORD cchWideChar; // ebx
  DWORD v15; // eax
  int v16; // eax
  _QWORD v18[3]; // [rsp+48h] [rbp-460h] BYREF
  LPWSTR lpWideCharStr; // [rsp+60h] [rbp-448h] BYREF
  _BYTE v20[1032]; // [rsp+68h] [rbp-440h] BYREF

  v18[2] = 0;
  v18[1] = this;
  v18[0] = 0;
  lpWideCharStr = 0;
  Library = LoadLibraryExW(a2, 0, 0x60u);
  if ( !Library )
  {
    Library = LoadLibraryExW(a2, 0, 2u);
    if ( !Library )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_19;
    }
  }
  ResourceW = FindResourceW(Library, a3, a4);
  v11 = ResourceW;
  if ( !ResourceW )
    goto LABEL_5;
  Resource = (const CHAR *)LoadResource(Library, ResourceW);
  if ( !Resource )
    goto LABEL_5;
  cchWideChar = SizeofResource(Library, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_13;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(-2147024362);
    }
    if ( 2 * (unsigned __int64)v15 <= 0x400 )
    {
LABEL_13:
      lpWideCharStr = (LPWSTR)v20;
    }
    else
    {
      _mm_lfence();
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpWideCharStr, 2LL * v15);
    }
    if ( lpWideCharStr )
    {
      _mm_lfence();
      v16 = MultiByteToWideChar(3u, 0, Resource, cchWideChar, lpWideCharStr, cchWideChar);
      if ( v16 )
      {
        lpWideCharStr[v16] = 0;
        v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v18, lpWideCharStr, a5);
        goto LABEL_17;
      }
LABEL_5:
      v12 = ATL::AtlHresultFromLastError();
LABEL_17:
      Error = v12;
      goto LABEL_18;
    }
  }
  Error = -2147024882;
LABEL_18:
  FreeLibrary(Library);
LABEL_19:
  if ( lpWideCharStr != (LPWSTR)v20 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpWideCharStr);
  return Error;
}

```

## disassembly

```asm
0x1400361c0  push    rbx
0x1400361c2  push    rsi
0x1400361c3  push    rdi
0x1400361c4  push    r14
0x1400361c6  push    r15
0x1400361c8  sub     rsp, 480h
0x1400361cf  mov     rax, cs:__security_cookie
0x1400361d6  xor     rax, rsp
0x1400361d9  mov     [rsp+4A8h+var_38], rax
0x1400361e1  mov     r15, r9
0x1400361e4  mov     r14, r8
0x1400361e7  mov     rbx, rdx
0x1400361ea  xor     edi, edi
0x1400361ec  mov     [rsp+4A8h+var_450], rdi
0x1400361f1  mov     [rsp+4A8h+var_458], rcx
0x1400361f6  mov     [rsp+4A8h+var_460], rdi
0x1400361fb  mov     [rsp+4A8h+var_448], rdi
0x140036200  xor     edx, edx; hFile
0x140036202  lea     r8d, [rdi+60h]; dwFlags
0x140036206  mov     rcx, rbx; lpLibFileName
0x140036209  call    cs:__imp_LoadLibraryExW
0x14003620f  mov     rsi, rax
0x140036212  mov     [rsp+4A8h+var_470], rax
0x140036217  test    rax, rax
0x14003621a  jnz     short loc_140036244
0x14003621c  xor     edx, edx; hFile
0x14003621e  lea     r8d, [rdi+2]; dwFlags
0x140036222  mov     rcx, rbx; lpLibFileName
0x140036225  call    cs:__imp_LoadLibraryExW
0x14003622b  mov     rsi, rax
0x14003622e  mov     [rsp+4A8h+var_470], rax
0x140036233  test    rax, rax
0x140036236  jnz     short loc_140036244
0x140036238  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14003623d  mov     ebx, eax
0x14003623f  jmp     loc_140036355
0x140036244  mov     r8, r15; lpType
0x140036247  mov     rdx, r14; lpName
0x14003624a  mov     rcx, rsi; hModule
0x14003624d  call    cs:__imp_FindResourceW
0x140036253  mov     rbx, rax
0x140036256  test    rax, rax
0x140036259  jnz     short loc_140036265
0x14003625b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140036260  jmp     loc_140036344
0x140036265  mov     rdx, rbx; hResInfo
0x140036268  mov     rcx, rsi; hModule
0x14003626b  call    cs:__imp_LoadResource
0x140036271  mov     r14, rax
0x140036274  mov     [rsp+4A8h+var_468], rax
0x140036279  test    rax, rax
0x14003627c  jz      short loc_14003625B
0x14003627e  mov     rdx, rbx; hResInfo
0x140036281  mov     rcx, rsi; hModule
0x140036284  call    cs:__imp_SizeofResource
0x14003628a  mov     ebx, eax
0x14003628c  mov     [rsp+4A8h+var_478], eax
0x140036290  inc     eax
0x140036292  cmp     eax, ebx
0x140036294  jnb     short loc_1400362A0
0x140036296  mov     ebx, 8007000Eh
0x14003629b  jmp     loc_140036346
0x1400362a0  mov     ecx, eax
0x1400362a2  test    eax, eax
0x1400362a4  jz      short loc_1400362D5
0x1400362a6  xor     edx, edx
0x1400362a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400362ac  div     rcx
0x1400362af  cmp     rax, 2
0x1400362b3  jb      loc_14003638D
0x1400362b9  lea     rdx, [rcx+rcx]
0x1400362bd  cmp     rdx, 400h
0x1400362c4  jbe     short loc_1400362D5
0x1400362c6  lfence
0x1400362c9  lea     rcx, [rsp+4A8h+var_448]
0x1400362ce  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400362d3  jmp     short loc_1400362DF
0x1400362d5  lea     rax, [rsp+4A8h+var_440]
0x1400362da  mov     [rsp+4A8h+var_448], rax
0x1400362df  jmp     short loc_1400362F1
0x1400362e1  xor     edi, edi
0x1400362e3  mov     rsi, [rsp+4A8h+var_470]
0x1400362e8  mov     r14, [rsp+4A8h+var_468]
0x1400362ed  mov     ebx, [rsp+4A8h+var_478]
0x1400362f1  cmp     [rsp+4A8h+var_448], rdi
0x1400362f6  jz      short loc_140036296
0x1400362f8  lfence
0x1400362fb  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x1400362ff  mov     rax, [rsp+4A8h+var_448]
0x140036304  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x140036309  mov     r9d, ebx; cbMultiByte
0x14003630c  mov     r8, r14; lpMultiByteStr
0x14003630f  xor     edx, edx; dwFlags
0x140036311  lea     ecx, [rdx+3]; CodePage
0x140036314  call    cs:__imp_MultiByteToWideChar
0x14003631a  test    eax, eax
0x14003631c  jz      loc_14003625B
0x140036322  mov     ecx, eax
0x140036324  mov     rax, [rsp+4A8h+var_448]
0x140036329  mov     [rax+rcx*2], di
0x14003632d  mov     r8d, [rsp+4A8h+arg_20]; int
0x140036335  mov     rdx, [rsp+4A8h+var_448]; unsigned __int16 *
0x14003633a  lea     rcx, [rsp+4A8h+var_460]; this
0x14003633f  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140036344  mov     ebx, eax
0x140036346  test    rsi, rsi
0x140036349  jz      short loc_140036355
0x14003634b  mov     rcx, rsi; hLibModule
0x14003634e  call    cs:__imp_FreeLibrary
0x140036354  nop
0x140036355  lea     rax, [rsp+4A8h+var_440]
0x14003635a  cmp     [rsp+4A8h+var_448], rax
0x14003635f  jz      short loc_14003636C
0x140036361  lea     rcx, [rsp+4A8h+var_448]
0x140036366  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14003636b  nop
0x14003636c  mov     eax, ebx
0x14003636e  mov     rcx, [rsp+4A8h+var_38]
0x140036376  xor     rcx, rsp; StackCookie
0x140036379  call    __security_check_cookie
0x14003637e  add     rsp, 480h
0x140036385  pop     r15
0x140036387  pop     r14
0x140036389  pop     rdi
0x14003638a  pop     rsi
0x14003638b  pop     rbx
0x14003638c  retn
0x14003638d  lfence
0x140036390  mov     ecx, 80070216h; int
0x140036395  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
