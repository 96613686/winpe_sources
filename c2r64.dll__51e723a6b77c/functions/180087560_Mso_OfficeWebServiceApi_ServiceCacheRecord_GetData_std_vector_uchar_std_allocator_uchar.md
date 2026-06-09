# Mso::OfficeWebServiceApi::ServiceCacheRecord::GetData(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180087560`
- end: `0x1800876a2`
- name: `?GetData@ServiceCacheRecord@OfficeWebServiceApi@Mso@@QEAA_NAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `322`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x180039e08`
- `0x18007e750`
- `0x18008a680`

## callees

- `0x18001c13c`
- `0x18001c6b4`
- `0x18001c760`
- `0x18003aa1c`
- `0x180087560`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x1800875d8`
- `KERNEL32!GetFileSizeEx` at `0x1800875d8`
- `KERNEL32!ReadFile` at `0x180087666`
- `KERNEL32!ReadFile` at `0x180087666`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Mso::OfficeWebServiceApi::ServiceCacheRecord::GetData(__int64 a1, __int64 *a2)
{
  const WCHAR *v3; // rcx
  __int64 *v4; // rdx
  __int64 v5; // r8
  char *FileW; // r14
  DWORD LowPart; // esi
  __int64 v9; // rdx
  __int64 v10; // r15
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  size_t v13; // rbx
  void *v14; // rax
  BOOL v15; // eax
  __int64 v17; // [rsp+0h] [rbp-68h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  char *v19; // [rsp+80h] [rbp+18h] BYREF
  LARGE_INTEGER FileSize; // [rsp+88h] [rbp+20h] BYREF

  if ( !*(_QWORD *)(a1 + 48) )
    return 0;
  v3 = (const WCHAR *)(a1 + 32);
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(const WCHAR **)v3;
  FileW = (char *)MsoCreateFileW(v3, 0x80000000, 1u, 0, 3u, 128);
  v19 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      try
      {
        LowPart = FileSize.LowPart;
        NumberOfBytesRead = 0;
        v9 = *a2;
        v10 = a2[1];
        v11 = v10 - *a2;
        if ( FileSize.LowPart < v11 )
        {
          v12 = v9 + FileSize.LowPart;
LABEL_13:
          a2[1] = v12;
          goto LABEL_14;
        }
        if ( FileSize.LowPart > v11 )
        {
          if ( FileSize.LowPart <= (unsigned __int64)(a2[2] - v9) )
          {
            v13 = FileSize.LowPart - v11;
            memset((void *)a2[1], 0, v13);
            v12 = v13 + v10;
            goto LABEL_13;
          }
          _mm_lfence();
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2);
        }
LABEL_14:
        v14 = (void *)std::vector<unsigned char>::operator[](a2, 0);
        v15 = ReadFile(FileW, v14, LowPart, &NumberOfBytesRead, 0);
      }
      catch ( std::bad_alloc )
      {
        v4 = &v17;
        goto LABEL_18;
      }
      if ( v15 && LowPart == NumberOfBytesRead )
      {
        std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v19, v4, v5);
        return 1;
      }
    }
  }
LABEL_18:
  std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(&v19, v4, v5);
  return 0;
}

```

## disassembly

```asm
0x180087560  push    rbx
0x180087562  push    rsi
0x180087563  push    rdi
0x180087564  push    r14
0x180087566  push    r15
0x180087568  sub     rsp, 40h
0x18008756c  mov     rdi, rdx
0x18008756f  cmp     qword ptr [rcx+30h], 0
0x180087574  jz      loc_180087694
0x18008757a  add     rcx, 20h ; ' '
0x18008757e  cmp     qword ptr [rcx+18h], 7
0x180087583  jbe     short loc_180087588
0x180087585  mov     rcx, [rcx]; lpFileName
0x180087588  mov     [rsp+68h+var_40], 80h; int
0x180087590  mov     dword ptr [rsp+68h+lpOverlapped], 3; DWORD
0x180087598  xor     r9d, r9d; lpSecurityAttributes
0x18008759b  mov     edx, 80000000h; dwDesiredAccess
0x1800875a0  lea     r8d, [r9+1]; dwShareMode
0x1800875a4  call    MsoCreateFileW
0x1800875a9  mov     r14, rax
0x1800875ac  mov     [rsp+68h+arg_10], rax
0x1800875b4  dec     rax
0x1800875b7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800875bb  ja      loc_180087687
0x1800875c1  mov     qword ptr [rsp+68h+FileSize], 0
0x1800875cd  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x1800875d5  mov     rcx, r14; hFile
0x1800875d8  call    cs:__imp_GetFileSizeEx
0x1800875de  test    eax, eax
0x1800875e0  jz      loc_180087687
0x1800875e6  mov     esi, dword ptr [rsp+68h+FileSize]
0x1800875ed  mov     [rsp+68h+NumberOfBytesRead], 0
0x1800875f5  mov     rdx, [rdi]
0x1800875f8  mov     r15, [rdi+8]
0x1800875fc  mov     rcx, r15
0x1800875ff  sub     rcx, rdx
0x180087602  mov     ebx, esi
0x180087604  cmp     rsi, rcx
0x180087607  jnb     short loc_18008760F
0x180087609  lea     rax, [rdx+rsi]
0x18008760d  jmp     short loc_180087641
0x18008760f  jbe     short loc_180087645
0x180087611  mov     rax, [rdi+10h]
0x180087615  sub     rax, rdx
0x180087618  cmp     rbx, rax
0x18008761b  jbe     short loc_18008762D
0x18008761d  lfence
0x180087620  mov     rdx, rbx
0x180087623  mov     rcx, rdi
0x180087626  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18008762b  jmp     short loc_180087645
0x18008762d  sub     rbx, rcx
0x180087630  mov     r8, rbx; Size
0x180087633  xor     edx, edx; Val
0x180087635  mov     rcx, r15; void *
0x180087638  call    memset
0x18008763d  lea     rax, [rbx+r15]
0x180087641  mov     [rdi+8], rax
0x180087645  xor     edx, edx
0x180087647  mov     rcx, rdi
0x18008764a  call    ??A?$vector@EV?$allocator@E@std@@@std@@QEAAAEAE_K@Z; std::vector<uchar>::operator[](unsigned __int64)
0x18008764f  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x180087658  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008765d  mov     r8d, esi; nNumberOfBytesToRead
0x180087660  mov     rdx, rax; lpBuffer
0x180087663  mov     rcx, r14; hFile
0x180087666  call    cs:__imp_ReadFile
0x18008766c  test    eax, eax
0x18008766e  jz      short loc_180087687
0x180087670  cmp     esi, [rsp+68h+NumberOfBytesRead]
0x180087674  jnz     short loc_180087687
0x180087676  lea     rcx, [rsp+68h+arg_10]
0x18008767e  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x180087683  mov     al, 1
0x180087685  jmp     short loc_180087696
0x180087687  lea     rcx, [rsp+68h+arg_10]
0x18008768f  call    ??1?$unique_ptr@PEAXUHandleDeleter@Win@Mso@@@std@@QEAA@XZ; std::unique_ptr<void *,Mso::Win::HandleDeleter>::~unique_ptr<void *,Mso::Win::HandleDeleter>(void)
0x180087694  xor     al, al
0x180087696  add     rsp, 40h
0x18008769a  pop     r15
0x18008769c  pop     r14
0x18008769e  pop     rdi
0x18008769f  pop     rsi
0x1800876a0  pop     rbx
0x1800876a1  retn
```
