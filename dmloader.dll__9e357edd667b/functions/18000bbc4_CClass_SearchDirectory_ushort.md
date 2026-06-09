# CClass::SearchDirectory(ushort *)

- ea: `0x18000bbc4`
- end: `0x18000c010`
- name: `?SearchDirectory@CClass@@QEAAJPEAG@Z`
- size: `1100`
- prototype: `__int64 __fastcall(CClass *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800099e0`

## callees

- `0x1800015d0`
- `0x180001ef0`
- `0x180009fdc`
- `0x18000a060`
- `0x18000a10c`
- `0x18000a310`
- `0x18000a484`
- `0x18000a584`
- `0x18000ad9c`
- `0x18000b358`
- `0x18000bbc4`
- `0x18000c018`
- `0x18000c290`
- `0x18000c70c`
- `0x18000cd7c`
- `0x18000d80c`
- `0x18000db40`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000bf04`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000bf04`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bc33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000beb6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000bc33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000beb6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bf96`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bf96`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000bf1b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000bf1b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bd47`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bd47`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bc1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000bc1d`

## pseudocode

```c
__int64 __fastcall CClass::SearchDirectory(CClass *this, unsigned __int16 *a2)
{
  HRESULT Path; // r14d
  CFileStream *v5; // rax
  CFileStream *v6; // r15
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r9
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  HANDLE FirstFileW; // r12
  CObject *v13; // rbx
  int Object; // eax
  struct CObject *v15; // rdi
  BOOL v16; // ecx
  BOOL v17; // eax
  CObject *v18; // rax
  CObject *v19; // rax
  FILE *v20; // rcx
  unsigned __int64 v21; // rdx
  int v22; // eax
  CObject *v23; // rax
  CObject *v24; // rcx
  struct CObject *v25; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  char v27[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  FILETIME ftLastWriteTime; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v30; // [rsp+90h] [rbp-70h]
  DWORD nFileSizeLow; // [rsp+98h] [rbp-68h]
  _BYTE v32[176]; // [rsp+F0h] [rbp-10h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp+A0h] BYREF
  int v34; // [rsp+3F0h] [rbp+2F0h] BYREF
  char v35[860]; // [rsp+3F4h] [rbp+2F4h] BYREF
  unsigned __int16 v36[2]; // [rsp+750h] [rbp+650h] BYREF
  wchar_t v37; // [rsp+754h] [rbp+654h]
  WCHAR FileName[520]; // [rsp+760h] [rbp+660h] BYREF

  ppv = 0;
  Path = CoCreateInstance((const IID *const)((char *)this + 36), 0, 1u, &IID_IDirectMusicObject, &ppv);
  if ( Path >= 0 )
  {
    v5 = (CFileStream *)malloc(0x230u);
    if ( v5 )
      v6 = CFileStream::CFileStream(v5, *((struct CLoader **)this + 23));
    else
      v6 = 0;
    Path = -2147024882;
    if ( v6 )
    {
      memset_0(FileName, 0, sizeof(FileName));
      Path = CClass::GetPath(this, FileName);
      if ( Path >= 0 )
      {
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        *(_DWORD *)v36 = *(_DWORD *)L"*.";
        v8 = -1;
        v37 = asc_1800121EC[2];
        v25 = 0;
        do
          ++v8;
        while ( v36[v8] );
        StringCchCatNW(FileName, v7, v36, v8);
        if ( a2 )
        {
          v9 = -1;
          do
            ++v9;
          while ( a2[v9] );
          v10 = -1;
          do
            ++v10;
          while ( FileName[v10] );
          if ( 519 - v10 > v9 )
            StringCchCatNW(FileName, v10, a2, 519 - v9);
        }
        FirstFileW = FindFirstFileW(FileName, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          CFileStream::Release(v6);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          return 1;
        }
        Path = 1;
        v13 = 0;
        CClass::ClearObjects(this, 1, a2);
        while ( 1 )
        {
          CDescriptor::CDescriptor((CDescriptor *)v27);
          CClass::GetPath(this, FileName);
          ftLastWriteTime = FindFileData.ftLastWriteTime;
          StringCchCatNW(FileName, v21, FindFileData.cFileName, 0x104u);
          v22 = CDescriptor::SetFileName((CDescriptor *)v27, FileName);
          if ( v22 < 0 )
            break;
          v28 = 304;
          Object = CClass::FindObject(this, (struct CDescriptor *)v27, &v25, 0, 0);
          v15 = v25;
          if ( Object < 0 )
            goto LABEL_26;
          v16 = FindFileData.nFileSizeLow != *((_DWORD *)v25 + 24)
             || *(_QWORD *)&FindFileData.ftLastWriteTime == *(_QWORD *)((char *)v25 + 52);
          v17 = 0;
          if ( !*((_QWORD *)v25 + 23) )
            v17 = v16;
          if ( v17 )
          {
LABEL_26:
            if ( (int)CFileStream::Open(v6, v30, 0x80000000) >= 0 )
            {
              memset_0(v35, 0, 0x354u);
              v34 = 856;
              if ( (*(int (__fastcall **)(LPVOID, CFileStream *, int *))(*(_QWORD *)ppv + 40LL))(ppv, v6, &v34) >= 0 )
              {
                Path = 0;
                CDescriptor::CDescriptor((CDescriptor *)v32);
                CDescriptor::Set((CDescriptor *)v32, (struct _DMUS_OBJECTDESC *)&v34, 0);
                CDescriptor::Merge((CDescriptor *)v27, (struct CDescriptor *)v32);
                nFileSizeLow = FindFileData.nFileSizeLow;
                ftLastWriteTime = FindFileData.ftLastWriteTime;
                if ( v15 )
                {
                  CDescriptor::Copy((struct CObject *)((char *)v15 + 8), (struct CDescriptor *)v27);
                  *((_DWORD *)v15 + 48) |= 0xCu;
                }
                else
                {
                  v18 = (CObject *)malloc(0xD8u);
                  if ( v18 )
                  {
                    v19 = CObject::CObject(v18, this, (struct CDescriptor *)v27);
                    v25 = v19;
                    if ( v19 )
                    {
                      *(_QWORD *)v19 = v13;
                      v13 = v19;
                      *((_DWORD *)v19 + 48) |= 0xCu;
                    }
                  }
                  else
                  {
                    v25 = 0;
                  }
                }
                CDescriptor::~CDescriptor((CDescriptor *)v32);
              }
              v20 = (FILE *)*((_QWORD *)v6 + 68);
              if ( v20 )
                fclose(v20);
              *((_QWORD *)v6 + 68) = 0;
            }
          }
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
            goto LABEL_42;
          CDescriptor::~CDescriptor((CDescriptor *)v27);
        }
        Path = v22;
LABEL_42:
        CDescriptor::~CDescriptor((CDescriptor *)v27);
        FindClose(FirstFileW);
        while ( v13 )
        {
          v23 = v13;
          v24 = v13;
          v13 = *(CObject **)v13;
          *(_QWORD *)v23 = 0;
          *(_QWORD *)v24 = *((_QWORD *)this + 25);
          *((_QWORD *)this + 25) = v24;
        }
        *((_DWORD *)this + 56) = 1;
      }
      CFileStream::Release(v6);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x18000bbc4  mov     [rsp-8+arg_10], rbx
0x18000bbc9  push    rbp
0x18000bbca  push    rsi
0x18000bbcb  push    rdi
0x18000bbcc  push    r12
0x18000bbce  push    r13
0x18000bbd0  push    r14
0x18000bbd2  push    r15
0x18000bbd4  lea     rbp, [rsp-0A80h]
0x18000bbdc  sub     rsp, 0B80h
0x18000bbe3  mov     rax, cs:__security_cookie
0x18000bbea  xor     rax, rsp
0x18000bbed  mov     [rbp+0AB0h+var_40], rax
0x18000bbf4  xor     r13d, r13d
0x18000bbf7  lea     rax, [rsp+0BB0h+var_B78]
0x18000bbfc  mov     rdi, rdx
0x18000bbff  mov     [rsp+0BB0h+var_B78], r13
0x18000bc04  mov     rsi, rcx
0x18000bc07  mov     [rsp+0BB0h+ppv], rax; ppv
0x18000bc0c  add     rcx, 24h ; '$'; rclsid
0x18000bc10  lea     r9, IID_IDirectMusicObject; riid
0x18000bc17  lea     r8d, [r13+1]; dwClsContext
0x18000bc1b  xor     edx, edx; pUnkOuter
0x18000bc1d  call    cs:__imp_CoCreateInstance
0x18000bc23  mov     r14d, eax
0x18000bc26  test    eax, eax
0x18000bc28  js      loc_18000BFE3
0x18000bc2e  mov     ecx, 230h; Size
0x18000bc33  call    cs:__imp_malloc
0x18000bc39  test    rax, rax
0x18000bc3c  jz      short loc_18000BC52
0x18000bc3e  mov     rdx, [rsi+0B8h]; struct CLoader *
0x18000bc45  mov     rcx, rax; this
0x18000bc48  call    ??0CFileStream@@QEAA@PEAVCLoader@@@Z; CFileStream::CFileStream(CLoader *)
0x18000bc4d  mov     r15, rax
0x18000bc50  jmp     short loc_18000BC55
0x18000bc52  mov     r15, r13
0x18000bc55  mov     r14d, 8007000Eh
0x18000bc5b  test    r15, r15
0x18000bc5e  jz      loc_18000BFD2
0x18000bc64  xor     edx, edx; Val
0x18000bc66  lea     rcx, [rbp+0AB0h+FileName]; void *
0x18000bc6d  mov     r8d, 410h; Size
0x18000bc73  call    memset_0
0x18000bc78  lea     rdx, [rbp+0AB0h+FileName]; unsigned __int16 *
0x18000bc7f  mov     rcx, rsi; this
0x18000bc82  call    ?GetPath@CClass@@QEAAJPEAG@Z; CClass::GetPath(ushort *)
0x18000bc87  mov     r14d, eax
0x18000bc8a  test    eax, eax
0x18000bc8c  js      loc_18000BFCA
0x18000bc92  xor     edx, edx; Val
0x18000bc94  lea     rcx, [rbp+0AB0h+FindFileData]; void *
0x18000bc9b  mov     r8d, 250h; Size
0x18000bca1  call    memset_0
0x18000bca6  mov     eax, dword ptr cs:asc_1800121EC; "*."
0x18000bcac  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000bcb0  mov     dword ptr [rbp+0AB0h+var_460], eax
0x18000bcb6  mov     r9, rbx
0x18000bcb9  movzx   eax, word ptr cs:asc_1800121EC+4; ""
0x18000bcc0  mov     [rbp+0AB0h+var_45C], ax
0x18000bcc7  lea     rax, [rbp+0AB0h+var_460]
0x18000bcce  mov     [rsp+0BB0h+var_B80], r13
0x18000bcd3  inc     r9; unsigned __int64
0x18000bcd6  cmp     [rax+r9*2], r13w
0x18000bcdb  jnz     short loc_18000BCD3
0x18000bcdd  lea     r8, [rbp+0AB0h+var_460]; unsigned __int16 *
0x18000bce4  lea     rcx, [rbp+0AB0h+FileName]; unsigned __int16 *
0x18000bceb  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000bcf0  test    rdi, rdi
0x18000bcf3  jz      short loc_18000BD39
0x18000bcf5  mov     rcx, rbx
0x18000bcf8  inc     rcx
0x18000bcfb  cmp     [rdi+rcx*2], r13w
0x18000bd00  jnz     short loc_18000BCF8
0x18000bd02  lea     rax, [rbp+0AB0h+FileName]
0x18000bd09  mov     rdx, rbx
0x18000bd0c  inc     rdx; unsigned __int64
0x18000bd0f  cmp     [rax+rdx*2], r13w
0x18000bd14  jnz     short loc_18000BD0C
0x18000bd16  mov     r9d, 207h
0x18000bd1c  mov     eax, r9d
0x18000bd1f  sub     rax, rdx
0x18000bd22  cmp     rax, rcx
0x18000bd25  jbe     short loc_18000BD39
0x18000bd27  sub     r9, rcx; unsigned __int64
0x18000bd2a  mov     r8, rdi; unsigned __int16 *
0x18000bd2d  lea     rcx, [rbp+0AB0h+FileName]; unsigned __int16 *
0x18000bd34  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000bd39  lea     rdx, [rbp+0AB0h+FindFileData]; lpFindFileData
0x18000bd40  lea     rcx, [rbp+0AB0h+FileName]; lpFileName
0x18000bd47  call    cs:__imp_FindFirstFileW
0x18000bd4d  mov     r12, rax
0x18000bd50  cmp     rax, rbx
0x18000bd53  jnz     short loc_18000BD78
0x18000bd55  mov     rcx, r15; this
0x18000bd58  call    ?Release@CFileStream@@UEAAKXZ; CFileStream::Release(void)
0x18000bd5d  mov     rcx, [rsp+0BB0h+var_B78]
0x18000bd62  mov     rdx, [rcx]
0x18000bd65  mov     rax, [rdx+10h]
0x18000bd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd6e  mov     eax, 1
0x18000bd73  jmp     loc_18000BFE6
0x18000bd78  mov     eax, 1
0x18000bd7d  mov     r8, rdi; unsigned __int16 *
0x18000bd80  mov     edx, eax; int
0x18000bd82  mov     rcx, rsi; this
0x18000bd85  mov     r14d, eax
0x18000bd88  mov     rbx, r13
0x18000bd8b  call    ?ClearObjects@CClass@@QEAAXHPEAG@Z; CClass::ClearObjects(int,ushort *)
0x18000bd90  jmp     loc_18000BF2F
0x18000bd95  xor     r9d, r9d; struct CObject *
0x18000bd98  mov     [rsp+0BB0h+var_B68], 130h
0x18000bda0  lea     r8, [rsp+0BB0h+var_B80]; struct CObject **
0x18000bda5  mov     [rsp+0BB0h+ppv], r13; struct IDirectMusicObject *
0x18000bdaa  lea     rdx, [rsp+0BB0h+var_B70]; struct CDescriptor *
0x18000bdaf  mov     rcx, rsi; this
0x18000bdb2  call    ?FindObject@CClass@@QEAAJPEAVCDescriptor@@PEAPEAVCObject@@PEAV3@PEAUIDirectMusicObject@@@Z; CClass::FindObject(CDescriptor *,CObject * *,CObject *,IDirectMusicObject *)
0x18000bdb7  mov     rdi, [rsp+0BB0h+var_B80]
0x18000bdbc  test    eax, eax
0x18000bdbe  js      short loc_18000BDF8
0x18000bdc0  mov     eax, [rdi+60h]
0x18000bdc3  cmp     [rbp+0AB0h+FindFileData.nFileSizeLow], eax
0x18000bdc9  jz      short loc_18000BDD2
0x18000bdcb  mov     ecx, 1
0x18000bdd0  jmp     short loc_18000BDE3
0x18000bdd2  mov     rax, qword ptr [rbp+0AB0h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000bdd9  mov     ecx, r13d
0x18000bddc  cmp     rax, [rdi+34h]
0x18000bde0  setz    cl
0x18000bde3  cmp     [rdi+0B8h], r13
0x18000bdea  mov     eax, r13d
0x18000bded  cmovz   eax, ecx
0x18000bdf0  test    eax, eax
0x18000bdf2  jz      loc_18000BF11
0x18000bdf8  mov     rdx, [rbp+0AB0h+var_B20]; unsigned __int16 *
0x18000bdfc  mov     r8d, 80000000h; unsigned int
0x18000be02  mov     rcx, r15; this
0x18000be05  call    ?Open@CFileStream@@QEAAJPEAGK@Z; CFileStream::Open(ushort *,ulong)
0x18000be0a  test    eax, eax
0x18000be0c  js      loc_18000BF11
0x18000be12  xor     edx, edx; Val
0x18000be14  lea     rcx, [rbp+0AB0h+var_7BC]; void *
0x18000be1b  mov     r8d, 354h; Size
0x18000be21  call    memset_0
0x18000be26  mov     rcx, [rsp+0BB0h+var_B78]
0x18000be2b  lea     r8, [rbp+0AB0h+var_7C0]
0x18000be32  mov     [rbp+0AB0h+var_7C0], 358h
0x18000be3c  mov     rdx, r15
0x18000be3f  mov     rax, [rcx]
0x18000be42  mov     rax, [rax+28h]
0x18000be46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be4b  test    eax, eax
0x18000be4d  js      loc_18000BEF8
0x18000be53  lea     rcx, [rbp+0AB0h+var_AC0]; this
0x18000be57  mov     r14d, r13d
0x18000be5a  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000be5f  xor     r8d, r8d; struct IStream *
0x18000be62  lea     rdx, [rbp+0AB0h+var_7C0]; struct _DMUS_OBJECTDESC *
0x18000be69  lea     rcx, [rbp+0AB0h+var_AC0]; this
0x18000be6d  call    ?Set@CDescriptor@@QEAAXPEAU_DMUS_OBJECTDESC@@PEAUIStream@@@Z; CDescriptor::Set(_DMUS_OBJECTDESC *,IStream *)
0x18000be72  lea     rdx, [rbp+0AB0h+var_AC0]; struct CDescriptor *
0x18000be76  lea     rcx, [rsp+0BB0h+var_B70]; this
0x18000be7b  call    ?Merge@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Merge(CDescriptor *)
0x18000be80  mov     eax, [rbp+0AB0h+FindFileData.nFileSizeLow]
0x18000be86  mov     [rbp+0AB0h+var_B18], eax
0x18000be89  mov     rax, qword ptr [rbp+0AB0h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000be90  mov     [rsp+0BB0h+var_B44], rax
0x18000be95  test    rdi, rdi
0x18000be98  jz      short loc_18000BEB1
0x18000be9a  lea     rcx, [rdi+8]; this
0x18000be9e  lea     rdx, [rsp+0BB0h+var_B70]; struct CDescriptor *
0x18000bea3  call    ?Copy@CDescriptor@@QEAAXPEAV1@@Z; CDescriptor::Copy(CDescriptor *)
0x18000bea8  or      dword ptr [rdi+0C0h], 0Ch
0x18000beaf  jmp     short loc_18000BEEF
0x18000beb1  mov     ecx, 0D8h; Size
0x18000beb6  call    cs:__imp_malloc
0x18000bebc  test    rax, rax
0x18000bebf  jz      short loc_18000BEEA
0x18000bec1  lea     r8, [rsp+0BB0h+var_B70]; struct CDescriptor *
0x18000bec6  mov     rdx, rsi; struct CClass *
0x18000bec9  mov     rcx, rax; this
0x18000becc  call    ??0CObject@@QEAA@PEAVCClass@@PEAVCDescriptor@@@Z; CObject::CObject(CClass *,CDescriptor *)
0x18000bed1  mov     [rsp+0BB0h+var_B80], rax
0x18000bed6  test    rax, rax
0x18000bed9  jz      short loc_18000BEEF
0x18000bedb  mov     [rax], rbx
0x18000bede  mov     rbx, rax
0x18000bee1  or      dword ptr [rax+0C0h], 0Ch
0x18000bee8  jmp     short loc_18000BEEF
0x18000beea  mov     [rsp+0BB0h+var_B80], r13
0x18000beef  lea     rcx, [rbp+0AB0h+var_AC0]; this
0x18000bef3  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000bef8  mov     rcx, [r15+220h]; Stream
0x18000beff  test    rcx, rcx
0x18000bf02  jz      short loc_18000BF0A
0x18000bf04  call    cs:__imp_fclose
0x18000bf0a  mov     [r15+220h], r13
0x18000bf11  lea     rdx, [rbp+0AB0h+FindFileData]; lpFindFileData
0x18000bf18  mov     rcx, r12; hFindFile
0x18000bf1b  call    cs:__imp_FindNextFileW
0x18000bf21  test    eax, eax
0x18000bf23  jz      short loc_18000BF89
0x18000bf25  lea     rcx, [rsp+0BB0h+var_B70]; this
0x18000bf2a  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000bf2f  lea     rcx, [rsp+0BB0h+var_B70]; this
0x18000bf34  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x18000bf39  lea     rdx, [rbp+0AB0h+FileName]; unsigned __int16 *
0x18000bf40  mov     rcx, rsi; this
0x18000bf43  call    ?GetPath@CClass@@QEAAJPEAG@Z; CClass::GetPath(ushort *)
0x18000bf48  mov     rax, qword ptr [rbp+0AB0h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18000bf4f  lea     r8, [rbp+0AB0h+FindFileData.cFileName]; unsigned __int16 *
0x18000bf56  mov     r9d, 104h; unsigned __int64
0x18000bf5c  mov     [rsp+0BB0h+var_B44], rax
0x18000bf61  lea     rcx, [rbp+0AB0h+FileName]; unsigned __int16 *
0x18000bf68  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000bf6d  lea     rdx, [rbp+0AB0h+FileName]; unsigned __int16 *
0x18000bf74  lea     rcx, [rsp+0BB0h+var_B70]; this
0x18000bf79  call    ?SetFileName@CDescriptor@@QEAAJPEAG@Z; CDescriptor::SetFileName(ushort *)
0x18000bf7e  test    eax, eax
0x18000bf80  jns     loc_18000BD95
0x18000bf86  mov     r14d, eax
0x18000bf89  lea     rcx, [rsp+0BB0h+var_B70]; this
0x18000bf8e  call    ??1CDescriptor@@QEAA@XZ; CDescriptor::~CDescriptor(void)
0x18000bf93  mov     rcx, r12; hFindFile
0x18000bf96  call    cs:__imp_FindClose
0x18000bf9c  test    rbx, rbx
0x18000bf9f  jz      short loc_18000BFC0
0x18000bfa1  mov     rax, rbx
0x18000bfa4  mov     rcx, rbx
0x18000bfa7  mov     rbx, [rbx]
0x18000bfaa  mov     [rax], r13
0x18000bfad  mov     rax, [rsi+0C8h]
0x18000bfb4  mov     [rcx], rax
0x18000bfb7  mov     [rsi+0C8h], rcx
0x18000bfbe  jmp     short loc_18000BF9C
0x18000bfc0  mov     dword ptr [rsi+0E0h], 1
0x18000bfca  mov     rcx, r15; this
0x18000bfcd  call    ?Release@CFileStream@@UEAAKXZ; CFileStream::Release(void)
0x18000bfd2  mov     rcx, [rsp+0BB0h+var_B78]
0x18000bfd7  mov     rax, [rcx]
0x18000bfda  mov     rax, [rax+10h]
0x18000bfde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe3  mov     eax, r14d
0x18000bfe6  mov     rcx, [rbp+0AB0h+var_40]
0x18000bfed  xor     rcx, rsp; StackCookie
0x18000bff0  call    __security_check_cookie
0x18000bff5  mov     rbx, [rsp+0BB0h+arg_10]
0x18000bffd  add     rsp, 0B80h
0x18000c004  pop     r15
0x18000c006  pop     r14
0x18000c008  pop     r13
0x18000c00a  pop     r12
0x18000c00c  pop     rdi
0x18000c00d  pop     rsi
0x18000c00e  pop     rbp
0x18000c00f  retn
```
