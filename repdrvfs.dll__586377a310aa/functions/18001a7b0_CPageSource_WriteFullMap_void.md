# CPageSource::WriteFullMap(void)

- ea: `0x18001a7b0`
- end: `0x18001aaea`
- name: `?WriteFullMap@CPageSource@@QEAAKXZ`
- size: `826`
- prototype: `unsigned int __fastcall(CPageSource *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ad80`

## callees

- `0x1800012b8`
- `0x18001a7b0`
- `0x180023b3c`
- `0x18002b7b6`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001a83d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001a83d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001aad4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001aad4`
- `wbemcomn!GetMemLogObject` at `0x18001a84b`
- `wbemcomn!GetMemLogObject` at `0x18001a84b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a85a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001a85a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18001aa9c`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18001aa9c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001aa86`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001aa86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aaa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aaa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aac9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPageSource::WriteFullMap(CPageSource *this)
{
  DWORD v3; // ebp
  _DWORD *v4; // rax
  _DWORD *v5; // r14
  CMemoryLog *MemLogObject; // rax
  DWORD LastError; // ebx
  unsigned __int64 v8; // rdx
  _DWORD *v9; // rdi
  __int64 i; // rax
  size_t v11; // rbx
  __int64 v12; // rcx
  char *v13; // rdi
  __int64 v14; // rbx
  char *v15; // rdi
  unsigned __int64 v16; // rdx
  char *v17; // rdi
  __int64 j; // rax
  size_t v19; // rbx
  __int64 v20; // rcx
  char *v21; // rdi
  __int64 v22; // rbx
  void *v23; // rbx
  void *v24[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp+10h] BYREF

  if ( !CPageSource::m_writeBit )
    return 0;
  v3 = 4
     * (((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 2)
      + ((__int64)(*((_QWORD *)this + 93) - *((_QWORD *)this + 92)) >> 2)
      + 6
      * (-1431655765 * ((__int64)(*((_QWORD *)this + 90) - *((_QWORD *)this + 89)) >> 3)
       - 1431655765 * ((__int64)(*((_QWORD *)this + 33) - *((_QWORD *)this + 32)) >> 3)))
     + 68;
  v4 = CWin32DefaultArena::WbemMemAlloc(v3);
  v5 = v4;
  if ( v4 )
  {
    v24[0] = v4;
    v24[1] = 0;
    *v4 = 43981;
    v4[1] = *((_DWORD *)this + 173);
    v4[2] = *((_DWORD *)this + 174);
    v4[3] = *((_DWORD *)this + 175);
    v4[4] = *((_DWORD *)this + 202);
    v8 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 90) - *((_QWORD *)this + 89)) >> 3);
    v4[5] = v8;
    v9 = v4 + 6;
    for ( i = *((_QWORD *)this + 89); i != *((_QWORD *)this + 90); i += 24 )
      *(_DWORD *)(i + 16) = *((_DWORD *)this + 174);
    v11 = 6LL * (unsigned int)v8;
    memcpy_0(v5 + 6, *((const void **)this + 89), v11 * 4);
    v12 = (unsigned int)((__int64)(*((_QWORD *)this + 93) - *((_QWORD *)this + 92)) >> 2);
    v9[v11] = v12;
    v13 = (char *)&v9[v11 + 1];
    v14 = 4 * v12;
    memcpy_0(v13, *((const void **)this + 92), 4 * v12);
    *(_DWORD *)&v13[v14] = 56506;
    v15 = &v13[v14];
    *((_DWORD *)v15 + 1) = 43981;
    *((_DWORD *)v15 + 2) = *((_DWORD *)this + 59);
    *((_DWORD *)v15 + 3) = *((_DWORD *)this + 60);
    *((_DWORD *)v15 + 4) = *((_DWORD *)this + 61);
    *((_DWORD *)v15 + 5) = *((_DWORD *)this + 88);
    v16 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 33) - *((_QWORD *)this + 32)) >> 3);
    *((_DWORD *)v15 + 6) = v16;
    v17 = v15 + 28;
    for ( j = *((_QWORD *)this + 32); j != *((_QWORD *)this + 33); j += 24 )
      *(_DWORD *)(j + 16) = *((_DWORD *)this + 60);
    v19 = 24LL * (unsigned int)v16;
    memcpy_0(v17, *((const void **)this + 32), v19);
    v20 = (unsigned int)((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 2);
    *(_DWORD *)&v17[v19] = v20;
    v21 = &v17[v19];
    v22 = 4 * v20;
    memcpy_0(v21 + 4, *((const void **)this + 35), 4 * v20);
    *(_DWORD *)&v21[v22 + 4] = 56506;
    *(_DWORD *)&v21[v22 + 8] = g_bShuttingDown;
    v23 = (void *)*((_QWORD *)this + *((unsigned int *)this + 253) + 121);
    NumberOfBytesWritten = 0;
    if ( WriteFile(v23, v5, v3, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v3 )
    {
      if ( SetEndOfFile(v23) )
      {
        CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v24);
        return 0;
      }
      LastError = GetLastError();
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v24);
    }
    else
    {
      LastError = GetLastError();
      CWin32DefaultArena::WbemMemFree(v5);
    }
  }
  else
  {
    MemLogObject = GetMemLogObject();
    LastError = 14;
    CMemoryLog::Write(MemLogObject, 14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18001a7b0  push    rbx
0x18001a7b2  push    rbp
0x18001a7b3  push    rsi
0x18001a7b4  push    rdi
0x18001a7b5  push    r13
0x18001a7b7  push    r14
0x18001a7b9  sub     rsp, 48h
0x18001a7bd  mov     rsi, rcx
0x18001a7c0  cmp     cs:?m_writeBit@CPageSource@@0KA, 0; ulong CPageSource::m_writeBit
0x18001a7c7  jnz     short loc_18001A7D0
0x18001a7c9  xor     eax, eax
0x18001a7cb  jmp     loc_18001AADD
0x18001a7d0  mov     rcx, [rcx+108h]
0x18001a7d7  sub     rcx, [rsi+100h]
0x18001a7de  sar     rcx, 3
0x18001a7e2  mov     r13, 0AAAAAAAAAAAAAAABh
0x18001a7ec  imul    rcx, r13
0x18001a7f0  mov     rax, [rsi+2D0h]
0x18001a7f7  sub     rax, [rsi+2C8h]
0x18001a7fe  sar     rax, 3
0x18001a802  imul    rax, r13
0x18001a806  add     ecx, eax
0x18001a808  lea     ecx, [rcx+rcx*2]
0x18001a80b  mov     rax, [rsi+2E8h]
0x18001a812  sub     rax, [rsi+2E0h]
0x18001a819  sar     rax, 2
0x18001a81d  lea     edx, [rax+rcx*2]
0x18001a820  mov     rax, [rsi+120h]
0x18001a827  sub     rax, [rsi+118h]
0x18001a82e  sar     rax, 2
0x18001a832  add     edx, eax
0x18001a834  lea     ebp, ds:44h[rdx*4]
0x18001a83b  mov     ecx, ebp
0x18001a83d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001a843  mov     r14, rax
0x18001a846  test    rax, rax
0x18001a849  jnz     short loc_18001A8A6
0x18001a84b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001a851  lea     ebx, [r14+0Eh]
0x18001a855  mov     edx, ebx
0x18001a857  mov     rcx, rax
0x18001a85a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001a860  lea     rax, WPP_GLOBAL_Control
0x18001a867  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a86e  cmp     rcx, rax
0x18001a871  jz      loc_18001AADB
0x18001a877  test    byte ptr [rcx+1Ch], 1
0x18001a87b  jz      loc_18001AADB
0x18001a881  cmp     byte ptr [rcx+19h], 2
0x18001a885  jb      loc_18001AADB
0x18001a88b  lea     edx, [rbx+6Bh]
0x18001a88e  mov     r9d, ebx
0x18001a891  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18001a898  mov     rcx, [rcx+10h]
0x18001a89c  call    WPP_SF_d
0x18001a8a1  jmp     loc_18001AADB
0x18001a8a6  mov     [rsp+78h+var_48], r14
0x18001a8ab  mov     [rsp+78h+var_40], 0
0x18001a8b4  mov     dword ptr [rax], 0ABCDh
0x18001a8ba  mov     eax, [rsi+2B4h]
0x18001a8c0  mov     [r14+4], eax
0x18001a8c4  lea     rdi, [r14+8]
0x18001a8c8  mov     eax, [rsi+2B8h]
0x18001a8ce  mov     [rdi], eax
0x18001a8d0  mov     eax, [rsi+2BCh]
0x18001a8d6  mov     [rdi+4], eax
0x18001a8d9  mov     eax, [rsi+328h]
0x18001a8df  mov     [rdi+8], eax
0x18001a8e2  mov     rdx, [rsi+2D0h]
0x18001a8e9  sub     rdx, [rsi+2C8h]
0x18001a8f0  sar     rdx, 3
0x18001a8f4  imul    rdx, r13
0x18001a8f8  mov     [rdi+0Ch], edx
0x18001a8fb  add     rdi, 10h
0x18001a8ff  mov     rax, [rsi+2C8h]
0x18001a906  cmp     rax, [rsi+2D0h]
0x18001a90d  jz      short loc_18001A91E
0x18001a90f  mov     ecx, [rsi+2B8h]
0x18001a915  mov     [rax+10h], ecx
0x18001a918  add     rax, 18h
0x18001a91c  jmp     short loc_18001A906
0x18001a91e  mov     eax, edx
0x18001a920  lea     rcx, [rax+rax*2]
0x18001a924  lea     rbx, ds:0[rcx*8]
0x18001a92c  mov     r8, rbx; Size
0x18001a92f  mov     rdx, [rsi+2C8h]; Src
0x18001a936  mov     rcx, rdi; void *
0x18001a939  call    memcpy_0
0x18001a93e  mov     rcx, [rsi+2E8h]
0x18001a945  sub     rcx, [rsi+2E0h]
0x18001a94c  sar     rcx, 2
0x18001a950  mov     ecx, ecx
0x18001a952  mov     [rbx+rdi], ecx
0x18001a955  add     rbx, 4
0x18001a959  add     rdi, rbx
0x18001a95c  lea     rbx, ds:0[rcx*4]
0x18001a964  mov     r8, rbx; Size
0x18001a967  mov     rdx, [rsi+2E0h]; Src
0x18001a96e  mov     rcx, rdi; void *
0x18001a971  call    memcpy_0
0x18001a976  mov     dword ptr [rbx+rdi], 0DCBAh
0x18001a97d  add     rdi, rbx
0x18001a980  mov     dword ptr [rdi+4], 0ABCDh
0x18001a987  mov     eax, [rsi+0ECh]
0x18001a98d  mov     [rdi+8], eax
0x18001a990  mov     eax, [rsi+0F0h]
0x18001a996  mov     [rdi+0Ch], eax
0x18001a999  mov     eax, [rsi+0F4h]
0x18001a99f  mov     [rdi+10h], eax
0x18001a9a2  mov     eax, [rsi+160h]
0x18001a9a8  mov     [rdi+14h], eax
0x18001a9ab  mov     rdx, [rsi+108h]
0x18001a9b2  sub     rdx, [rsi+100h]
0x18001a9b9  sar     rdx, 3
0x18001a9bd  imul    rdx, r13
0x18001a9c1  mov     [rdi+18h], edx
0x18001a9c4  add     rdi, 1Ch
0x18001a9c8  mov     rax, [rsi+100h]
0x18001a9cf  cmp     rax, [rsi+108h]
0x18001a9d6  jz      short loc_18001A9E7
0x18001a9d8  mov     ecx, [rsi+0F0h]
0x18001a9de  mov     [rax+10h], ecx
0x18001a9e1  add     rax, 18h
0x18001a9e5  jmp     short loc_18001A9CF
0x18001a9e7  mov     eax, edx
0x18001a9e9  lea     rcx, [rax+rax*2]
0x18001a9ed  lea     rbx, ds:0[rcx*8]
0x18001a9f5  mov     r8, rbx; Size
0x18001a9f8  mov     rdx, [rsi+100h]; Src
0x18001a9ff  mov     rcx, rdi; void *
0x18001aa02  call    memcpy_0
0x18001aa07  mov     rcx, [rsi+120h]
0x18001aa0e  sub     rcx, [rsi+118h]
0x18001aa15  sar     rcx, 2
0x18001aa19  mov     ecx, ecx
0x18001aa1b  mov     [rbx+rdi], ecx
0x18001aa1e  add     rdi, rbx
0x18001aa21  lea     rbx, ds:0[rcx*4]
0x18001aa29  mov     r8, rbx; Size
0x18001aa2c  mov     rdx, [rsi+118h]; Src
0x18001aa33  lea     rcx, [rdi+4]; void *
0x18001aa37  call    memcpy_0
0x18001aa3c  mov     dword ptr [rbx+rdi+4], 0DCBAh
0x18001aa44  xor     eax, eax
0x18001aa46  cmp     cs:?g_bShuttingDown@@3_NA, al; bool g_bShuttingDown
0x18001aa4c  setnz   al
0x18001aa4f  mov     [rbx+rdi+8], eax
0x18001aa53  mov     eax, [rsi+3F4h]
0x18001aa59  mov     rbx, [rsi+rax*8+3C8h]
0x18001aa61  mov     [rsp+78h+NumberOfBytesWritten], 0
0x18001aa6c  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18001aa75  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001aa7d  mov     r8d, ebp; nNumberOfBytesToWrite
0x18001aa80  mov     rdx, r14; lpBuffer
0x18001aa83  mov     rcx, rbx; hFile
0x18001aa86  call    cs:__imp_WriteFile
0x18001aa8c  test    eax, eax
0x18001aa8e  jz      short loc_18001AAC9
0x18001aa90  cmp     [rsp+78h+NumberOfBytesWritten], ebp
0x18001aa97  jnz     short loc_18001AAC9
0x18001aa99  mov     rcx, rbx; hFile
0x18001aa9c  call    cs:__imp_SetEndOfFile
0x18001aaa2  test    eax, eax
0x18001aaa4  jnz     short loc_18001AABA
0x18001aaa6  call    cs:__imp_GetLastError
0x18001aaac  mov     ebx, eax
0x18001aaae  lea     rcx, [rsp+78h+var_48]
0x18001aab3  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18001aab8  jmp     short loc_18001AADB
0x18001aaba  lea     rcx, [rsp+78h+var_48]
0x18001aabf  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18001aac4  jmp     loc_18001A7C9
0x18001aac9  call    cs:__imp_GetLastError
0x18001aacf  mov     ebx, eax
0x18001aad1  mov     rcx, r14
0x18001aad4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001aada  nop
0x18001aadb  mov     eax, ebx
0x18001aadd  add     rsp, 48h
0x18001aae1  pop     r14
0x18001aae3  pop     r13
0x18001aae5  pop     rdi
0x18001aae6  pop     rsi
0x18001aae7  pop     rbp
0x18001aae8  pop     rbx
0x18001aae9  retn
```
