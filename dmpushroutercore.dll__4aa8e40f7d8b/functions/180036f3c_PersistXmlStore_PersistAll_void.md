# PersistXmlStore::PersistAll(void)

- ea: `0x180036f3c`
- end: `0x1800371c2`
- name: `?PersistAll@PersistXmlStore@@AEAAJXZ`
- size: `646`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x1800364f0`
- `0x1800365e0`
- `0x180036710`
- `0x180037480`

## callees

- `0x180036f3c`
- `0x180037668`
- `0x180037c28`
- `0x180037e8c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003719e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003719e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037181`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180037181`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037198`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037198`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180037172`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180037172`
- `XmlLite!CreateXmlWriter` at `0x180036fb5`
- `XmlLite!CreateXmlWriter` at `0x180036fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistXmlStore::PersistAll(PersistXmlStore *this)
{
  __int64 v2; // r14
  __int64 v3; // rbp
  __int64 v4; // rcx
  const WCHAR *v5; // rsi
  const unsigned __int16 *v6; // rcx
  struct IStream *FileStream; // r15
  HRESULT v8; // ebx
  void *v9; // rax
  __int64 v10; // r14
  __int64 v11; // rbp
  int v12; // ebp
  __int64 v13; // rcx
  __int64 v14; // rcx
  const WCHAR *v15; // rdx
  const WCHAR *v16; // rcx
  signed int LastError; // eax
  void *ppvObject; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 12);
  v3 = *((_QWORD *)this + 11);
  ppvObject = 0;
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 9) = 0;
  }
  v5 = (const WCHAR *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) <= 7u )
    v6 = (const unsigned __int16 *)((char *)this + 40);
  else
    v6 = *(const unsigned __int16 **)v5;
  FileStream = CreateFileStream(v6, 1);
  if ( FileStream )
  {
    v8 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, FileStream);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 3, 1);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
          if ( v8 >= 0 )
          {
            v9 = ppvObject;
            ppvObject = 0;
            *((_QWORD *)this + 9) = v9;
          }
        }
      }
    }
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)FileStream + 16LL))(FileStream);
  }
  else
  {
    v8 = -2147024882;
  }
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( v8 >= 0 )
  {
    v10 = (v2 - v3) >> 3;
    v8 = PersistXmlStore::WriteXmlRootElement(this, v10);
    if ( v8 >= 0 )
    {
      v11 = 0;
      if ( (int)v10 <= 0 )
      {
LABEL_21:
        v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 120LL))(*((_QWORD *)this + 9));
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 112LL))(*((_QWORD *)this + 9));
          if ( v8 >= 0 )
            v8 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 248LL))(*((_QWORD *)this + 9));
        }
        if ( v8 >= 0 )
        {
          v12 = 10;
          v13 = *((_QWORD *)this + 10);
          if ( v13 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 24LL))(v13, 0);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 16LL))(*((_QWORD *)this + 10));
            *((_QWORD *)this + 10) = 0;
          }
          v14 = *((_QWORD *)this + 9);
          if ( v14 )
          {
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, 0);
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 16LL))(*((_QWORD *)this + 9));
            *((_QWORD *)this + 9) = 0;
          }
          while ( v12 )
          {
            v15 = (const WCHAR *)((char *)this + 8);
            if ( *((_QWORD *)this + 4) > 7u )
              v15 = *(const WCHAR **)v15;
            if ( *((_QWORD *)this + 8) <= 7u )
              v16 = (const WCHAR *)((char *)this + 40);
            else
              v16 = *(const WCHAR **)v5;
            if ( MoveFileExW(v16, v15, 3u) )
              return (unsigned int)v8;
            Sleep(0x3E8u);
            --v12;
          }
          if ( *((_QWORD *)this + 8) > 7u )
            v5 = *(const WCHAR **)v5;
          DeleteFileW(v5);
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
        while ( 1 )
        {
          v8 = PersistXmlStore::WriteItem(this, *(struct PersistObject **)(*((_QWORD *)this + 11) + 8 * v11));
          if ( v8 < 0 )
            break;
          v11 = (unsigned int)(v11 + 1);
          if ( (int)v11 >= (int)v10 )
            goto LABEL_21;
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036f3c  push    rbx
0x180036f3e  push    rbp
0x180036f3f  push    rsi
0x180036f40  push    rdi
0x180036f41  push    r14
0x180036f43  push    r15
0x180036f45  sub     rsp, 28h
0x180036f49  mov     rdi, rcx
0x180036f4c  mov     r14, [rcx+60h]
0x180036f50  mov     rbp, [rcx+58h]
0x180036f54  mov     [rsp+58h+ppvObject], 0
0x180036f5d  mov     rcx, [rcx+48h]
0x180036f61  test    rcx, rcx
0x180036f64  jz      short loc_180036F7A
0x180036f66  mov     rax, [rcx]
0x180036f69  mov     rax, [rax+10h]
0x180036f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f72  mov     qword ptr [rdi+48h], 0
0x180036f7a  lea     rsi, [rdi+28h]
0x180036f7e  cmp     qword ptr [rsi+18h], 7
0x180036f83  jbe     short loc_180036F8A
0x180036f85  mov     rcx, [rsi]
0x180036f88  jmp     short loc_180036F8D
0x180036f8a  mov     rcx, rsi; unsigned __int16 *
0x180036f8d  mov     dl, 1; bool
0x180036f8f  call    ?CreateFileStream@@YAPEAUIStream@@PEBG_N@Z; CreateFileStream(ushort const *,bool)
0x180036f94  mov     r15, rax
0x180036f97  test    rax, rax
0x180036f9a  jnz     short loc_180036FA6
0x180036f9c  mov     ebx, 8007000Eh
0x180036fa1  jmp     loc_18003703C
0x180036fa6  xor     r8d, r8d; pMalloc
0x180036fa9  lea     rdx, [rsp+58h+ppvObject]; ppvObject
0x180036fae  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180036fb5  call    cs:__imp_CreateXmlWriter
0x180036fbb  mov     ebx, eax
0x180036fbd  test    eax, eax
0x180036fbf  js      short loc_18003702C
0x180036fc1  mov     rcx, [rsp+58h+ppvObject]
0x180036fc6  mov     rax, [rcx]
0x180036fc9  mov     rdx, r15
0x180036fcc  mov     rax, [rax+18h]
0x180036fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fd5  mov     ebx, eax
0x180036fd7  test    eax, eax
0x180036fd9  js      short loc_18003702C
0x180036fdb  mov     rcx, [rsp+58h+ppvObject]
0x180036fe0  mov     rax, [rcx]
0x180036fe3  mov     edx, 3
0x180036fe8  lea     r8d, [rdx-2]
0x180036fec  mov     rax, [rax+28h]
0x180036ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ff5  mov     ebx, eax
0x180036ff7  test    eax, eax
0x180036ff9  js      short loc_18003702C
0x180036ffb  mov     rcx, [rsp+58h+ppvObject]
0x180037000  mov     rax, [rcx]
0x180037003  mov     edx, 1
0x180037008  mov     r8d, edx
0x18003700b  mov     rax, [rax+28h]
0x18003700f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037014  mov     ebx, eax
0x180037016  test    eax, eax
0x180037018  js      short loc_18003702C
0x18003701a  mov     rax, [rsp+58h+ppvObject]
0x18003701f  mov     [rsp+58h+ppvObject], 0
0x180037028  mov     [rdi+48h], rax
0x18003702c  mov     rax, [r15]
0x18003702f  mov     rcx, r15
0x180037032  mov     rax, [rax+10h]
0x180037036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003703b  nop
0x18003703c  mov     rcx, [rsp+58h+ppvObject]
0x180037041  test    rcx, rcx
0x180037044  jz      short loc_180037053
0x180037046  mov     rax, [rcx]
0x180037049  mov     rax, [rax+10h]
0x18003704d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037052  nop
0x180037053  test    ebx, ebx
0x180037055  js      loc_1800371B3
0x18003705b  sub     r14, rbp
0x18003705e  sar     r14, 3
0x180037062  mov     edx, r14d; unsigned int
0x180037065  mov     rcx, rdi; this
0x180037068  call    ?WriteXmlRootElement@PersistXmlStore@@AEAAJK@Z; PersistXmlStore::WriteXmlRootElement(ulong)
0x18003706d  mov     ebx, eax
0x18003706f  test    eax, eax
0x180037071  js      loc_1800371B3
0x180037077  xor     ebp, ebp
0x180037079  test    r14d, r14d
0x18003707c  jle     short loc_18003709F
0x18003707e  mov     rdx, [rdi+58h]
0x180037082  mov     rdx, [rdx+rbp*8]; struct PersistObject *
0x180037086  mov     rcx, rdi; this
0x180037089  call    ?WriteItem@PersistXmlStore@@AEAAJPEAVPersistObject@@@Z; PersistXmlStore::WriteItem(PersistObject *)
0x18003708e  mov     ebx, eax
0x180037090  test    eax, eax
0x180037092  js      loc_1800371B3
0x180037098  inc     ebp
0x18003709a  cmp     ebp, r14d
0x18003709d  jl      short loc_18003707E
0x18003709f  mov     rcx, [rdi+48h]
0x1800370a3  mov     rax, [rcx]
0x1800370a6  mov     rax, [rax+78h]
0x1800370aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370af  mov     ebx, eax
0x1800370b1  test    eax, eax
0x1800370b3  js      short loc_1800370E0
0x1800370b5  mov     rcx, [rdi+48h]
0x1800370b9  mov     rax, [rcx]
0x1800370bc  mov     rax, [rax+70h]
0x1800370c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370c5  mov     ebx, eax
0x1800370c7  test    eax, eax
0x1800370c9  js      short loc_1800370E0
0x1800370cb  mov     rcx, [rdi+48h]
0x1800370cf  mov     rax, [rcx]
0x1800370d2  mov     rax, [rax+0F8h]
0x1800370d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370de  mov     ebx, eax
0x1800370e0  test    ebx, ebx
0x1800370e2  js      loc_1800371B3
0x1800370e8  mov     ebp, 0Ah
0x1800370ed  mov     rcx, [rdi+50h]
0x1800370f1  test    rcx, rcx
0x1800370f4  jz      short loc_18003711C
0x1800370f6  mov     rax, [rcx]
0x1800370f9  xor     edx, edx
0x1800370fb  mov     rax, [rax+18h]
0x1800370ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037104  mov     rcx, [rdi+50h]
0x180037108  mov     rax, [rcx]
0x18003710b  mov     rax, [rax+10h]
0x18003710f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037114  mov     qword ptr [rdi+50h], 0
0x18003711c  mov     rcx, [rdi+48h]
0x180037120  test    rcx, rcx
0x180037123  jz      short loc_18003714B
0x180037125  mov     rax, [rcx]
0x180037128  xor     edx, edx
0x18003712a  mov     rax, [rax+18h]
0x18003712e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037133  mov     rcx, [rdi+48h]
0x180037137  mov     rax, [rcx]
0x18003713a  mov     rax, [rax+10h]
0x18003713e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037143  mov     qword ptr [rdi+48h], 0
0x18003714b  test    ebp, ebp
0x18003714d  jz      short loc_18003718B
0x18003714f  lea     rdx, [rdi+8]
0x180037153  cmp     qword ptr [rdi+20h], 7
0x180037158  jbe     short loc_18003715D
0x18003715a  mov     rdx, [rdx]; lpNewFileName
0x18003715d  cmp     qword ptr [rdi+40h], 7
0x180037162  jbe     short loc_180037169
0x180037164  mov     rcx, [rsi]
0x180037167  jmp     short loc_18003716C
0x180037169  mov     rcx, rsi; lpExistingFileName
0x18003716c  mov     r8d, 3; dwFlags
0x180037172  call    cs:__imp_MoveFileExW
0x180037178  test    eax, eax
0x18003717a  jnz     short loc_1800371B3
0x18003717c  mov     ecx, 3E8h; dwMilliseconds
0x180037181  call    cs:__imp_Sleep
0x180037187  dec     ebp
0x180037189  jmp     short loc_18003714B
0x18003718b  cmp     qword ptr [rsi+18h], 7
0x180037190  jbe     short loc_180037195
0x180037192  mov     rsi, [rsi]
0x180037195  mov     rcx, rsi; lpFileName
0x180037198  call    cs:__imp_DeleteFileW
0x18003719e  call    cs:__imp_GetLastError
0x1800371a4  mov     ebx, eax
0x1800371a6  test    eax, eax
0x1800371a8  jle     short loc_1800371B3
0x1800371aa  movzx   ebx, ax
0x1800371ad  or      ebx, 80070000h
0x1800371b3  mov     eax, ebx
0x1800371b5  add     rsp, 28h
0x1800371b9  pop     r15
0x1800371bb  pop     r14
0x1800371bd  pop     rdi
0x1800371be  pop     rsi
0x1800371bf  pop     rbp
0x1800371c0  pop     rbx
0x1800371c1  retn
```
