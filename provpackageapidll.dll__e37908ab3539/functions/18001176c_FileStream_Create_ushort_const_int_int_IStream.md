# FileStream::Create(ushort const *,int,int,IStream * *)

- ea: `0x18001176c`
- end: `0x1800118a5`
- name: `?Create@FileStream@@SAJPEBGHHPEAPEAUIStream@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, int, struct IStream **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800130cc`
- `0x1800131ac`

## callees

- `0x180002084`
- `0x180004a64`
- `0x180004a84`
- `0x18001176c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011844`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001183c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001185d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001183c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001185d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011890`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800117b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800117b9`

## pseudocode

```c
__int64 __fastcall FileStream::Create(const unsigned __int16 *a1, int a2, int a3, struct IStream **a4)
{
  HANDLE FileW; // rsi
  const char *v6; // r9
  struct IStream *v8; // rax
  struct IStream *v9; // rdi
  void **p_lpVtbl; // r14
  void *v11; // rbp
  DWORD LastError; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-68h]
  char v14; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a4 = 0;
  FileW = CreateFileW(a1, a2 != 0 ? 0x40000000 : 0x80000000, 3u, 0, 3 - (unsigned int)(a3 != 0), 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1F,
             (unsigned int)"onecore\\base\\ntsetup\\provpackageapi\\inc\\FileStream.h",
             v6);
  v8 = (struct IStream *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    LODWORD(v8[2].lpVtbl) = 1;
    v8->lpVtbl = (struct IStreamVtbl *)&FileStream::`vftable';
    p_lpVtbl = (void **)&v8[1].lpVtbl;
    v8[1].lpVtbl = (struct IStreamVtbl *)-1LL;
    if ( &v8[1] == (struct IStream *)&v14 )
    {
      *a4 = v8;
      if ( FileW )
        CloseHandle(FileW);
    }
    else
    {
      v11 = *p_lpVtbl;
      if ( (char *)*p_lpVtbl - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v11);
        SetLastError(LastError);
      }
      *p_lpVtbl = FileW;
      *a4 = v9;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\base\\ntsetup\\provpackageapi\\inc\\FileStream.h",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( FileW )
      CloseHandle(FileW);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001176c  push    rbx
0x18001176e  push    rbp
0x18001176f  push    rsi
0x180011770  push    rdi
0x180011771  push    r14
0x180011773  push    r15
0x180011775  sub     rsp, 58h
0x180011779  neg     r8d
0x18001177c  mov     qword ptr [r9], 0
0x180011783  mov     r8d, 3; dwShareMode
0x180011789  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180011792  sbb     eax, eax
0x180011794  mov     [rsp+88h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18001179c  add     eax, r8d
0x18001179f  mov     r15, r9
0x1800117a2  neg     edx
0x1800117a4  mov     [rsp+88h+dwCreationDisposition], eax; int
0x1800117a8  sbb     edx, edx
0x1800117aa  xor     r9d, r9d; lpSecurityAttributes
0x1800117ad  and     edx, 0C0000000h
0x1800117b3  add     edx, 80000000h; dwDesiredAccess
0x1800117b9  call    cs:__imp_CreateFileW
0x1800117bf  mov     rsi, rax
0x1800117c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800117c6  jnz     short loc_1800117E4
0x1800117c8  mov     rcx, [rsp+88h]; this
0x1800117d0  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\provpackageapi"...
0x1800117d7  lea     edx, [rax+20h]; void *
0x1800117da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800117df  jmp     loc_180011898
0x1800117e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800117eb  mov     ecx, 18h; unsigned __int64
0x1800117f0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800117f5  mov     rdi, rax
0x1800117f8  test    rax, rax
0x1800117fb  jz      short loc_180011867
0x1800117fd  lea     rax, ??_7FileStream@@6B@; const FileStream::`vftable'
0x180011804  mov     dword ptr [rdi+10h], 1
0x18001180b  mov     [rdi], rax
0x18001180e  lea     r14, [rdi+8]
0x180011812  lea     rax, [rsp+88h+var_48]
0x180011817  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18001181f  cmp     r14, rax
0x180011822  jz      short loc_180011852
0x180011824  mov     rbp, [r14]
0x180011827  lea     rdx, [rbp-1]
0x18001182b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001182f  ja      short loc_18001184A
0x180011831  call    cs:__imp_GetLastError
0x180011837  mov     rcx, rbp; hObject
0x18001183a  mov     ebx, eax
0x18001183c  call    cs:__imp_CloseHandle
0x180011842  mov     ecx, ebx; dwErrCode
0x180011844  call    cs:__imp_SetLastError
0x18001184a  mov     [r14], rsi
0x18001184d  mov     [r15], rdi
0x180011850  jmp     short loc_180011863
0x180011852  mov     [r15], rdi
0x180011855  test    rsi, rsi
0x180011858  jz      short loc_180011863
0x18001185a  mov     rcx, rsi; hObject
0x18001185d  call    cs:__imp_CloseHandle
0x180011863  xor     eax, eax
0x180011865  jmp     short loc_180011898
0x180011867  mov     rcx, [rsp+88h]; this
0x18001186f  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\provpackageapi"...
0x180011876  mov     ebx, 8007000Eh
0x18001187b  mov     edx, 23h ; '#'; void *
0x180011880  mov     r9d, ebx; char *
0x180011883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011888  test    rsi, rsi
0x18001188b  jz      short loc_180011896
0x18001188d  mov     rcx, rsi; hObject
0x180011890  call    cs:__imp_CloseHandle
0x180011896  mov     eax, ebx
0x180011898  add     rsp, 58h
0x18001189c  pop     r15
0x18001189e  pop     r14
0x1800118a0  pop     rdi
0x1800118a1  pop     rsi
0x1800118a2  pop     rbp
0x1800118a3  pop     rbx
0x1800118a4  retn
```
