# CPageMap::Save(void *)

- ea: `0x18002fb0c`
- end: `0x18002fcd1`
- name: `?Save@CPageMap@@QEAAKPEAX@Z`
- size: `453`
- prototype: `unsigned int(CPageMap *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002d080`

## callees

- `0x1800012b8`
- `0x180023b3c`
- `0x18002b7b6`
- `0x18002fb0c`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002fb54`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002fb54`
- `wbemcomn!GetMemLogObject` at `0x18002fb62`
- `wbemcomn!GetMemLogObject` at `0x18002fb62`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002fb71`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002fb71`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002fc8f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002fc8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb0`

## pseudocode

```c
__int64 __fastcall CPageMap::Save(CPageMap *this, void *a2)
{
  DWORD v4; // ebp
  _DWORD *v5; // rax
  _DWORD *v6; // r14
  CMemoryLog *MemLogObject; // rax
  DWORD LastError; // ebx
  unsigned __int64 v9; // rdx
  _DWORD *v10; // rdi
  __int64 v11; // rax
  size_t v12; // rbx
  __int64 v13; // rcx
  _DWORD *v14; // rdi
  __int64 v15; // rbx
  void *v17[9]; // [rsp+30h] [rbp-48h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+8h] BYREF

  v4 = 4
     * (((__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 2)
      + 2 * ((__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 3))
     + 32;
  v5 = CWin32DefaultArena::WbemMemAlloc(v4);
  v6 = v5;
  if ( v5 )
  {
    *v5 = 43981;
    v5[1] = *(_DWORD *)this;
    v5[2] = *((_DWORD *)this + 1);
    v5[3] = *((_DWORD *)this + 2);
    v5[4] = *((_DWORD *)this + 22);
    v9 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 3);
    v17[0] = v5;
    v5[5] = v9;
    v10 = v5 + 6;
    v11 = *((_QWORD *)this + 2);
    v17[1] = 0;
    while ( v11 != *((_QWORD *)this + 3) )
    {
      *(_DWORD *)(v11 + 16) = *((_DWORD *)this + 1);
      v11 += 24;
    }
    v12 = 6LL * (unsigned int)v9;
    memcpy_0(v6 + 6, *((const void **)this + 2), v12 * 4);
    v13 = (unsigned int)((__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 2);
    v10[v12] = v13;
    v14 = &v10[v12];
    v15 = v13;
    memcpy_0(v14 + 1, *((const void **)this + 5), 4 * v13);
    v14[v15 + 1] = 56506;
    NumberOfBytesWritten = 0;
    if ( WriteFile(a2, v6, v4, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v4 )
    {
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v17);
      return 0;
    }
    LastError = GetLastError();
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v17);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 14);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18002fb0c  push    rbx
0x18002fb0e  push    rbp
0x18002fb0f  push    rsi
0x18002fb10  push    rdi
0x18002fb11  push    r14
0x18002fb13  push    r15
0x18002fb15  sub     rsp, 48h
0x18002fb19  mov     rax, [rcx+18h]
0x18002fb1d  mov     rsi, rcx
0x18002fb20  sub     rax, [rcx+10h]
0x18002fb24  mov     rbx, 0AAAAAAAAAAAAAAABh
0x18002fb2e  sar     rax, 3
0x18002fb32  mov     r15, rdx
0x18002fb35  imul    rax, rbx
0x18002fb39  lea     ecx, [rax+rax*2]
0x18002fb3c  mov     rax, [rsi+30h]
0x18002fb40  sub     rax, [rsi+28h]
0x18002fb44  sar     rax, 2
0x18002fb48  lea     eax, [rax+rcx*2]
0x18002fb4b  lea     ebp, ds:20h[rax*4]
0x18002fb52  mov     ecx, ebp
0x18002fb54  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002fb5a  mov     r14, rax
0x18002fb5d  test    rax, rax
0x18002fb60  jnz     short loc_18002FBBD
0x18002fb62  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002fb68  lea     ebx, [r14+0Eh]
0x18002fb6c  mov     rcx, rax
0x18002fb6f  mov     edx, ebx
0x18002fb71  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002fb77  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb7e  lea     rax, WPP_GLOBAL_Control
0x18002fb85  cmp     rcx, rax
0x18002fb88  jz      loc_18002FCC2
0x18002fb8e  test    byte ptr [rcx+1Ch], 1
0x18002fb92  jz      loc_18002FCC2
0x18002fb98  cmp     byte ptr [rcx+19h], 2
0x18002fb9c  jb      loc_18002FCC2
0x18002fba2  mov     rcx, [rcx+10h]
0x18002fba6  lea     edx, [rbx+0Bh]
0x18002fba9  mov     r9d, ebx
0x18002fbac  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x18002fbb3  call    WPP_SF_d
0x18002fbb8  jmp     loc_18002FCC2
0x18002fbbd  mov     dword ptr [rax], 0ABCDh
0x18002fbc3  lea     rdi, [r14+8]
0x18002fbc7  mov     eax, [rsi]
0x18002fbc9  mov     [r14+4], eax
0x18002fbcd  mov     eax, [rsi+4]
0x18002fbd0  mov     [rdi], eax
0x18002fbd2  mov     eax, [rsi+8]
0x18002fbd5  mov     [rdi+4], eax
0x18002fbd8  mov     eax, [rsi+58h]
0x18002fbdb  mov     [rdi+8], eax
0x18002fbde  mov     rdx, [rsi+18h]
0x18002fbe2  sub     rdx, [rsi+10h]
0x18002fbe6  sar     rdx, 3
0x18002fbea  imul    rdx, rbx
0x18002fbee  mov     [rsp+78h+var_48], r14
0x18002fbf3  mov     [rdi+0Ch], edx
0x18002fbf6  add     rdi, 10h
0x18002fbfa  mov     rax, [rsi+10h]
0x18002fbfe  mov     [rsp+78h+var_40], 0
0x18002fc07  cmp     rax, [rsi+18h]
0x18002fc0b  jz      short loc_18002FC19
0x18002fc0d  mov     ecx, [rsi+4]
0x18002fc10  mov     [rax+10h], ecx
0x18002fc13  add     rax, 18h
0x18002fc17  jmp     short loc_18002FC07
0x18002fc19  mov     eax, edx
0x18002fc1b  mov     rdx, [rsi+10h]; Src
0x18002fc1f  lea     rcx, [rax+rax*2]
0x18002fc23  lea     rbx, ds:0[rcx*8]
0x18002fc2b  mov     rcx, rdi; void *
0x18002fc2e  mov     r8, rbx; Size
0x18002fc31  call    memcpy_0
0x18002fc36  mov     rcx, [rsi+30h]
0x18002fc3a  sub     rcx, [rsi+28h]
0x18002fc3e  sar     rcx, 2
0x18002fc42  mov     ecx, ecx
0x18002fc44  mov     [rbx+rdi], ecx
0x18002fc47  add     rdi, rbx
0x18002fc4a  mov     rdx, [rsi+28h]; Src
0x18002fc4e  lea     rbx, ds:0[rcx*4]
0x18002fc56  lea     rcx, [rdi+4]; void *
0x18002fc5a  mov     r8, rbx; Size
0x18002fc5d  call    memcpy_0
0x18002fc62  mov     dword ptr [rbx+rdi+4], 0DCBAh
0x18002fc6a  lea     r9, [rsp+78h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002fc72  mov     r8d, ebp; nNumberOfBytesToWrite
0x18002fc75  mov     [rsp+78h+NumberOfBytesWritten], 0
0x18002fc80  mov     rdx, r14; lpBuffer
0x18002fc83  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002fc8c  mov     rcx, r15; hFile
0x18002fc8f  call    cs:__imp_WriteFile
0x18002fc95  test    eax, eax
0x18002fc97  jz      short loc_18002FCB0
0x18002fc99  cmp     [rsp+78h+NumberOfBytesWritten], ebp
0x18002fca0  jnz     short loc_18002FCB0
0x18002fca2  lea     rcx, [rsp+78h+var_48]
0x18002fca7  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18002fcac  xor     eax, eax
0x18002fcae  jmp     short loc_18002FCC4
0x18002fcb0  call    cs:__imp_GetLastError
0x18002fcb6  lea     rcx, [rsp+78h+var_48]
0x18002fcbb  mov     ebx, eax
0x18002fcbd  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18002fcc2  mov     eax, ebx
0x18002fcc4  add     rsp, 48h
0x18002fcc8  pop     r15
0x18002fcca  pop     r14
0x18002fccc  pop     rdi
0x18002fccd  pop     rsi
0x18002fcce  pop     rbp
0x18002fccf  pop     rbx
0x18002fcd0  retn
```
