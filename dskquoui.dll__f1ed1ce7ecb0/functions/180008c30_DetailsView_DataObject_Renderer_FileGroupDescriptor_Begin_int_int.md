# DetailsView::DataObject::Renderer_FileGroupDescriptor::Begin(int,int)

- ea: `0x180008c30`
- end: `0x180008e04`
- name: `?Begin@Renderer_FileGroupDescriptor@DataObject@DetailsView@@MEAAXHH@Z`
- size: `468`
- prototype: `void __fastcall(DetailsView::DataObject::Renderer_FileGroupDescriptor *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001510`
- `0x1800022b4`
- `0x180008c30`
- `0x180010c70`
- `0x180019dd0`
- `0x180019ee0`
- `0x18001a468`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180008cee`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180008cee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DetailsView::DataObject::Renderer_FileGroupDescriptor::Begin(
        DetailsView::DataObject::Renderer_FileGroupDescriptor *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int16 *v5; // r8
  __int64 v6; // rdx
  char *v7; // rax
  __int16 v8; // r9
  char *v9; // rcx
  LPDWORD lpMaximumComponentLength; // [rsp+20h] [rbp-E0h]
  DWORD VolumeSerialNumber; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 **v13; // [rsp+50h] [rbp-B0h]
  _QWORD v14[2]; // [rsp+58h] [rbp-A8h] BYREF
  void **v15; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h]
  void **v17; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  char v19; // [rsp+88h] [rbp-78h]
  unsigned __int8 v20[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v21[72]; // [rsp+94h] [rbp-6Ch] BYREF
  char v22; // [rsp+DCh] [rbp-24h] BYREF
  WCHAR VolumeNameBuffer[40]; // [rsp+2F0h] [rbp+1F0h] BYREF

  memset_0(VolumeNameBuffer, 0, 0x42u);
  VolumeSerialNumber = 0;
  v2 = *((_QWORD *)this + 1);
  v14[0] = &CString::`vftable';
  v3 = *(_QWORD *)(v2 + 256);
  v14[1] = v3;
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 12));
  v15 = &CString::`vftable';
  v16 = *(_QWORD *)(v2 + 272);
  _InterlockedIncrement((volatile signed __int32 *)(v16 + 12));
  v17 = &CString::`vftable';
  v18 = *(_QWORD *)(v2 + 288);
  _InterlockedIncrement((volatile signed __int32 *)(v18 + 12));
  v19 = *(_BYTE *)(v2 + 296);
  GetVolumeInformationW(*(LPCWSTR *)v3, VolumeNameBuffer, 0x21u, &VolumeSerialNumber, 0, 0, 0, 0);
  CString::~CString((CString *)&v17);
  CString::~CString((CString *)&v15);
  CString::~CString((CString *)v14);
  CString::CString((CString *)v12);
  if ( VolumeNameBuffer[0] )
  {
    CString::Format((CString *)v12, g_hInstDll, 0x9E8Eu, VolumeNameBuffer);
  }
  else
  {
    LODWORD(lpMaximumComponentLength) = (unsigned __int16)VolumeSerialNumber;
    CString::Format((CString *)v12, g_hInstDll, 0x9EBDu, HIWORD(VolumeSerialNumber), lpMaximumComponentLength);
  }
  memset_0(v21, 0, 0x250u);
  *(_DWORD *)v20 = 1;
  v4 = 2147483646;
  v5 = *v13;
  v6 = 260;
  v7 = &v22;
  do
  {
    if ( !v4 )
      break;
    v8 = *v5;
    if ( !*v5 )
      break;
    ++v5;
    *(_WORD *)v7 = v8;
    v7 += 2;
    --v4;
    --v6;
  }
  while ( v6 );
  v9 = v7 - 2;
  if ( v6 )
    v9 = v7;
  *(_WORD *)v9 = 0;
  DetailsView::DataObject::Renderer::Stream::Write(
    (DetailsView::DataObject::Renderer_FileGroupDescriptor *)((char *)this + 16),
    v20,
    596);
  CString::~CString((CString *)v12);
}

```

## disassembly

```asm
0x180008c30  mov     [rsp-8+arg_8], rbx
0x180008c35  mov     [rsp-8+arg_10], rdi
0x180008c3a  push    rbp
0x180008c3b  lea     rbp, [rsp-250h]
0x180008c43  sub     rsp, 350h
0x180008c4a  mov     rax, cs:__security_cookie
0x180008c51  xor     rax, rsp
0x180008c54  mov     [rbp+250h+var_10], rax
0x180008c5b  mov     rbx, rcx
0x180008c5e  xor     edx, edx; Val
0x180008c60  lea     r8d, [rdx+42h]; Size
0x180008c64  lea     rcx, [rbp+250h+VolumeNameBuffer]; void *
0x180008c6b  call    memset_0
0x180008c70  xor     edi, edi
0x180008c72  mov     [rsp+350h+VolumeSerialNumber], edi
0x180008c76  mov     rdx, [rbx+8]
0x180008c7a  lea     r8, ??_7CString@@6B@; const CString::`vftable'
0x180008c81  mov     [rsp+350h+var_2F8], r8
0x180008c86  mov     rcx, [rdx+100h]
0x180008c8d  mov     [rsp+350h+var_2F0], rcx
0x180008c92  lock inc dword ptr [rcx+0Ch]
0x180008c96  mov     [rsp+350h+var_2E8], r8
0x180008c9b  mov     rax, [rdx+110h]
0x180008ca2  mov     [rsp+350h+var_2E0], rax
0x180008ca7  lock inc dword ptr [rax+0Ch]
0x180008cab  mov     [rsp+350h+var_2D8], r8
0x180008cb0  mov     rax, [rdx+120h]
0x180008cb7  mov     [rbp+250h+var_2D0], rax
0x180008cbb  lock inc dword ptr [rax+0Ch]
0x180008cbf  mov     al, [rdx+128h]
0x180008cc5  mov     [rbp+250h+var_2C8], al
0x180008cc8  mov     [rsp+350h+nFileSystemNameSize], edi; nFileSystemNameSize
0x180008ccc  mov     [rsp+350h+lpFileSystemNameBuffer], rdi; lpFileSystemNameBuffer
0x180008cd1  mov     [rsp+350h+lpFileSystemFlags], rdi; lpFileSystemFlags
0x180008cd6  mov     [rsp+350h+lpMaximumComponentLength], rdi; lpMaximumComponentLength
0x180008cdb  lea     r9, [rsp+350h+VolumeSerialNumber]; lpVolumeSerialNumber
0x180008ce0  lea     r8d, [rdi+21h]; nVolumeNameSize
0x180008ce4  lea     rdx, [rbp+250h+VolumeNameBuffer]; lpVolumeNameBuffer
0x180008ceb  mov     rcx, [rcx]; lpRootPathName
0x180008cee  call    cs:__imp_GetVolumeInformationW
0x180008cf4  lea     rcx, [rsp+350h+var_2D8]; this
0x180008cf9  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180008cfe  lea     rcx, [rsp+350h+var_2E8]; this
0x180008d03  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180008d08  lea     rcx, [rsp+350h+var_2F8]; this
0x180008d0d  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180008d12  lea     rcx, [rsp+350h+var_308]; this
0x180008d17  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180008d1c  nop
0x180008d1d  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180008d24  lea     rcx, [rsp+350h+var_308]; this
0x180008d29  cmp     di, [rbp+250h+VolumeNameBuffer]
0x180008d30  jz      short loc_180008D46
0x180008d32  lea     r9, [rbp+250h+VolumeNameBuffer]
0x180008d39  mov     r8d, 9E8Eh; unsigned int
0x180008d3f  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x180008d44  jmp     short loc_180008D62
0x180008d46  mov     r9d, [rsp+350h+VolumeSerialNumber]
0x180008d4b  movzx   eax, r9w
0x180008d4f  shr     r9d, 10h
0x180008d53  mov     dword ptr [rsp+350h+lpMaximumComponentLength], eax
0x180008d57  mov     r8d, 9EBDh; unsigned int
0x180008d5d  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x180008d62  xor     edx, edx; Val
0x180008d64  mov     r8d, 250h; Size
0x180008d6a  lea     rcx, [rbp+250h+var_2BC]; void *
0x180008d6e  call    memset_0
0x180008d73  mov     dword ptr [rbp+250h+var_2C0], 1
0x180008d7a  mov     ecx, 7FFFFFFEh
0x180008d7f  mov     rax, [rsp+350h+var_300]
0x180008d84  mov     r8, [rax]
0x180008d87  mov     edx, 104h
0x180008d8c  lea     rax, [rbp+250h+var_274]
0x180008d90  test    rcx, rcx
0x180008d93  jz      short loc_180008DB4
0x180008d95  movzx   r9d, word ptr [r8]
0x180008d99  test    r9w, r9w
0x180008d9d  jz      short loc_180008DB4
0x180008d9f  add     r8, 2
0x180008da3  mov     [rax], r9w
0x180008da7  add     rax, 2
0x180008dab  dec     rcx
0x180008dae  sub     rdx, 1
0x180008db2  jnz     short loc_180008D90
0x180008db4  lea     rcx, [rax-2]
0x180008db8  test    rdx, rdx
0x180008dbb  cmovnz  rcx, rax
0x180008dbf  mov     [rcx], di
0x180008dc2  lea     rcx, [rbx+10h]; this
0x180008dc6  mov     r8d, 254h; unsigned int
0x180008dcc  lea     rdx, [rbp+250h+var_2C0]; unsigned __int8 *
0x180008dd0  call    ?Write@Stream@Renderer@DataObject@DetailsView@@QEAAXPEBEI@Z; DetailsView::DataObject::Renderer::Stream::Write(uchar const *,uint)
0x180008dd5  nop
0x180008dd6  lea     rcx, [rsp+350h+var_308]; this
0x180008ddb  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180008de0  mov     rcx, [rbp+250h+var_10]
0x180008de7  xor     rcx, rsp; StackCookie
0x180008dea  call    __security_check_cookie
0x180008def  lea     r11, [rsp+350h+var_s0]
0x180008df7  mov     rbx, [r11+18h]
0x180008dfb  mov     rdi, [r11+20h]
0x180008dff  mov     rsp, r11
0x180008e02  pop     rbp
0x180008e03  retn
```
