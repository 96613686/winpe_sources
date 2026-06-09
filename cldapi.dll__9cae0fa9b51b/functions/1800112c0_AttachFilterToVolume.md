# AttachFilterToVolume

- ea: `0x1800112c0`
- end: `0x18001158d`
- name: `AttachFilterToVolume`
- size: `717`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180004dd0`
- `0x1800064e0`

## callees

- `0x18000231e`
- `0x1800046bc`
- `0x1800112c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011302`
- `ntdll!RtlNtStatusToDosError` at `0x1800113e7`
- `ntdll!RtlNtStatusToDosError` at `0x18001145e`
- `ntdll!RtlNtStatusToDosError` at `0x1800114d4`
- `ntdll!RtlNtStatusToDosError` at `0x180011302`
- `ntdll!RtlNtStatusToDosError` at `0x1800113e7`
- `ntdll!RtlNtStatusToDosError` at `0x18001145e`
- `ntdll!RtlNtStatusToDosError` at `0x1800114d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011552`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011328`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011552`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011346`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011346`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011566`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011566`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011541`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011541`
- `FLTLIB!FilterSendMessage` at `0x180011520`
- `FLTLIB!FilterSendMessage` at `0x180011520`

## pseudocode

```c
__int64 __fastcall AttachFilterToVolume(__int64 a1, __int64 a2)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  int v4; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v6; // rdi
  NTSTATUS v7; // esi
  NTSTATUS v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // ecx
  signed int v12; // eax
  NTSTATUS v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  __int64 v17; // rcx
  HANDLE v18; // rdx
  __int64 v19; // rax
  signed int v20; // eax
  HANDLE v21; // rax
  __int64 dwOutBufferSize; // [rsp+20h] [rbp-68h]
  __int64 v24; // [rsp+30h] [rbp-58h]
  DWORD BytesReturned; // [rsp+98h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+A0h] [rbp+18h] BYREF

  hObject = (HANDLE)-1LL;
  BytesReturned = 0;
  v2 = CfpCreateFile(a1, a2, 0, 7u, dwOutBufferSize, 0x21u, v24, &hObject);
  v3 = RtlNtStatusToDosError(v2);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    v6 = 0;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 8u, 0xD8u);
    v4 = v6 == 0 ? 8 : 0;
    if ( !v6 )
      v4 |= 0x80070000;
    if ( v4 >= 0 )
    {
      *(_QWORD *)v6 = 1886219331;
      v6[2] = 200;
      v6[3] = 1507328;
      memset_0(v6 + 4, 0, 0xB8u);
      v7 = -1073741811;
      if ( *((_WORD *)v6 + 7) )
      {
        v9 = (unsigned int)v6[2];
        if ( ((v9 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xD8 )
        {
          v11 = (v9 + 3) & 0xFFFFFFFC;
          v10 = v11;
          v6[2] = v11;
          v6[5] = v11;
          v8 = 0;
          v6[4] = 65543;
          *((_BYTE *)v6 + v10) = 1;
          ++v6[2];
        }
        else
        {
          v8 = -1073741789;
        }
      }
      else
      {
        v8 = -1073741811;
      }
      v12 = RtlNtStatusToDosError(v8);
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 >= 0 )
      {
        if ( *((_WORD *)v6 + 7) > 1u )
        {
          v14 = (unsigned int)v6[2];
          if ( ((v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xD8 )
          {
            v15 = ((_DWORD)v14 + 3) & 0xFFFFFFFC;
            v6[2] = v15;
            if ( *((_WORD *)v6 + 12) )
              *((_WORD *)v6 + 6) |= 1u;
            v6[6] = 131080;
            v13 = 0;
            v6[7] = v15;
            *(_WORD *)((char *)v6 + v15) = 1;
            v6[2] += 2;
          }
          else
          {
            v13 = -1073741789;
          }
        }
        else
        {
          v13 = -1073741811;
        }
        v16 = RtlNtStatusToDosError(v13);
        v4 = v16;
        if ( v16 > 0 )
          v4 = (unsigned __int16)v16 | 0x80070000;
        if ( v4 >= 0 )
        {
          if ( *((_WORD *)v6 + 7) > 2u )
          {
            v17 = (unsigned int)v6[2];
            if ( ((v17 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xD8 )
            {
              v18 = hObject;
              v19 = ((_DWORD)v17 + 3) & 0xFFFFFFFC;
              v6[2] = v19;
              if ( *((_WORD *)v6 + 16) )
                *((_WORD *)v6 + 6) |= 1u;
              v6[8] = 524299;
              v7 = 0;
              v6[9] = v19;
              *(_QWORD *)((char *)v6 + v19) = v18;
              v6[2] += 8;
            }
            else
            {
              v7 = -1073741789;
            }
          }
          v20 = RtlNtStatusToDosError(v7);
          v4 = v20;
          if ( v20 > 0 )
            v4 = (unsigned __int16)v20 | 0x80070000;
          if ( v4 >= 0 )
          {
            v6[1] = 0;
            *((_WORD *)v6 + 6) &= ~2u;
            v4 = FilterSendMessage(hPort, v6, 0xD8u, 0, 0, &BytesReturned);
          }
        }
      }
    }
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v6 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800112c0  mov     rax, rsp
0x1800112c3  mov     [rax+8], rbx
0x1800112c7  push    rbp
0x1800112c8  push    rsi
0x1800112c9  push    rdi
0x1800112ca  push    r12
0x1800112cc  push    r13
0x1800112ce  push    r14
0x1800112d0  push    r15
0x1800112d2  sub     rsp, 50h
0x1800112d6  xor     ebp, ebp
0x1800112d8  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800112e0  mov     [rax+10h], ebp
0x1800112e3  lea     rax, [rax+18h]
0x1800112e7  mov     [rsp+88h+var_50], rax
0x1800112ec  xor     r8d, r8d
0x1800112ef  mov     dword ptr [rsp+88h+lpBytesReturned], 21h ; '!'
0x1800112f7  lea     r9d, [rbp+7]
0x1800112fb  call    CfpCreateFile
0x180011300  mov     ecx, eax; Status
0x180011302  call    cs:__imp_RtlNtStatusToDosError
0x180011309  nop     dword ptr [rax+rax+00h]
0x18001130e  mov     ebx, eax
0x180011310  mov     r12d, 80070000h
0x180011316  test    eax, eax
0x180011318  jle     short loc_180011320
0x18001131a  movzx   ebx, ax
0x18001131d  or      ebx, r12d
0x180011320  test    ebx, ebx
0x180011322  js      loc_180011530
0x180011328  call    cs:__imp_GetProcessHeap
0x18001132f  nop     dword ptr [rax+rax+00h]
0x180011334  mov     r13d, 8
0x18001133a  mov     r8d, 0D8h; dwBytes
0x180011340  mov     rcx, rax; hHeap
0x180011343  mov     edx, r13d; dwFlags
0x180011346  call    cs:__imp_HeapAlloc
0x18001134d  nop     dword ptr [rax+rax+00h]
0x180011352  mov     rdi, rax
0x180011355  neg     rax
0x180011358  sbb     ebx, ebx
0x18001135a  not     ebx
0x18001135c  and     ebx, r13d
0x18001135f  mov     eax, ebx
0x180011361  or      eax, r12d
0x180011364  test    rdi, rdi
0x180011367  cmovz   ebx, eax
0x18001136a  test    ebx, ebx
0x18001136c  js      loc_180011533
0x180011372  xor     edx, edx; Val
0x180011374  mov     qword ptr [rdi], 706D6C43h
0x18001137b  mov     r8d, 0B8h; Size
0x180011381  mov     dword ptr [rdi+8], 0C8h
0x180011388  lea     rcx, [rdi+10h]; void *
0x18001138c  mov     dword ptr [rdi+0Ch], 170000h
0x180011393  call    memset_0
0x180011398  lea     r14d, [r13-7]
0x18001139c  mov     esi, 0C000000Dh
0x1800113a1  cmp     bp, [rdi+0Eh]
0x1800113a5  jb      short loc_1800113AB
0x1800113a7  mov     ecx, esi
0x1800113a9  jmp     short loc_1800113E7
0x1800113ab  mov     ecx, [rdi+8]
0x1800113ae  lea     rax, [rcx+3]
0x1800113b2  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800113b6  add     rax, r14
0x1800113b9  cmp     rax, 0D8h
0x1800113bf  jbe     short loc_1800113C8
0x1800113c1  mov     ecx, 0C0000023h
0x1800113c6  jmp     short loc_1800113E7
0x1800113c8  lea     eax, [rcx+3]
0x1800113cb  and     eax, 0FFFFFFFCh
0x1800113ce  mov     ecx, eax
0x1800113d0  mov     [rdi+8], ecx
0x1800113d3  mov     [rdi+14h], ecx
0x1800113d6  mov     ecx, ebp; Status
0x1800113d8  mov     dword ptr [rdi+10h], 10007h
0x1800113df  mov     [rax+rdi], r14b
0x1800113e3  add     [rdi+8], r14d
0x1800113e7  call    cs:__imp_RtlNtStatusToDosError
0x1800113ee  nop     dword ptr [rax+rax+00h]
0x1800113f3  mov     ebx, eax
0x1800113f5  test    eax, eax
0x1800113f7  jle     short loc_1800113FF
0x1800113f9  movzx   ebx, ax
0x1800113fc  or      ebx, r12d
0x1800113ff  test    ebx, ebx
0x180011401  js      loc_180011533
0x180011407  mov     r15d, 2
0x18001140d  cmp     r14w, [rdi+0Eh]
0x180011412  jb      short loc_180011418
0x180011414  mov     ecx, esi
0x180011416  jmp     short loc_18001145E
0x180011418  mov     ecx, [rdi+8]
0x18001141b  lea     rax, [rcx+3]
0x18001141f  and     rax, 0FFFFFFFFFFFFFFFCh
0x180011423  add     rax, r15
0x180011426  cmp     rax, 0D8h
0x18001142c  jbe     short loc_180011435
0x18001142e  mov     ecx, 0C0000023h
0x180011433  jmp     short loc_18001145E
0x180011435  lea     eax, [rcx+3]
0x180011438  and     eax, 0FFFFFFFCh
0x18001143b  mov     [rdi+8], eax
0x18001143e  cmp     [rdi+18h], bp
0x180011442  jz      short loc_180011449
0x180011444  or      [rdi+0Ch], r14w
0x180011449  mov     dword ptr [rdi+18h], 20008h
0x180011450  mov     ecx, ebp; Status
0x180011452  mov     [rdi+1Ch], eax
0x180011455  mov     [rax+rdi], r14w
0x18001145a  add     [rdi+8], r15d
0x18001145e  call    cs:__imp_RtlNtStatusToDosError
0x180011465  nop     dword ptr [rax+rax+00h]
0x18001146a  mov     ebx, eax
0x18001146c  test    eax, eax
0x18001146e  jle     short loc_180011476
0x180011470  movzx   ebx, ax
0x180011473  or      ebx, r12d
0x180011476  test    ebx, ebx
0x180011478  js      loc_180011533
0x18001147e  cmp     r15w, [rdi+0Eh]
0x180011483  jnb     short loc_1800114D2
0x180011485  mov     ecx, [rdi+8]
0x180011488  lea     rax, [rcx+3]
0x18001148c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180011490  add     rax, r13
0x180011493  cmp     rax, 0D8h
0x180011499  jbe     short loc_1800114A2
0x18001149b  mov     esi, 0C0000023h
0x1800114a0  jmp     short loc_1800114D2
0x1800114a2  mov     rdx, [rsp+88h+hObject]
0x1800114aa  lea     eax, [rcx+3]
0x1800114ad  and     eax, 0FFFFFFFCh
0x1800114b0  mov     [rdi+8], eax
0x1800114b3  cmp     [rdi+20h], bp
0x1800114b7  jz      short loc_1800114BE
0x1800114b9  or      [rdi+0Ch], r14w
0x1800114be  mov     dword ptr [rdi+20h], 8000Bh
0x1800114c5  mov     esi, ebp
0x1800114c7  mov     [rdi+24h], eax
0x1800114ca  mov     [rax+rdi], rdx
0x1800114ce  add     [rdi+8], r13d
0x1800114d2  mov     ecx, esi; Status
0x1800114d4  call    cs:__imp_RtlNtStatusToDosError
0x1800114db  nop     dword ptr [rax+rax+00h]
0x1800114e0  mov     ebx, eax
0x1800114e2  test    eax, eax
0x1800114e4  jle     short loc_1800114EC
0x1800114e6  movzx   ebx, ax
0x1800114e9  or      ebx, r12d
0x1800114ec  test    ebx, ebx
0x1800114ee  js      short loc_180011533
0x1800114f0  mov     eax, 0FFFDh
0x1800114f5  mov     [rdi+4], ebp
0x1800114f8  and     [rdi+0Ch], ax
0x1800114fc  xor     r9d, r9d; lpOutBuffer
0x1800114ff  mov     rcx, qword ptr cs:hPort; hPort
0x180011506  lea     rax, [rsp+88h+BytesReturned]
0x18001150e  mov     [rsp+88h+lpBytesReturned], rax; lpBytesReturned
0x180011513  mov     r8d, 0D8h; dwInBufferSize
0x180011519  mov     rdx, rdi; lpInBuffer
0x18001151c  mov     dword ptr [rsp+88h+dwOutBufferSize], ebp; dwOutBufferSize
0x180011520  call    cs:__imp_FilterSendMessage
0x180011527  nop     dword ptr [rax+rax+00h]
0x18001152c  mov     ebx, eax
0x18001152e  jmp     short loc_180011533
0x180011530  mov     rdi, rbp
0x180011533  mov     rcx, [rsp+88h+hObject]; hObject
0x18001153b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001153f  jz      short loc_18001154D
0x180011541  call    cs:__imp_CloseHandle
0x180011548  nop     dword ptr [rax+rax+00h]
0x18001154d  test    rdi, rdi
0x180011550  jz      short loc_180011572
0x180011552  call    cs:__imp_GetProcessHeap
0x180011559  nop     dword ptr [rax+rax+00h]
0x18001155e  mov     r8, rdi; lpMem
0x180011561  xor     edx, edx; dwFlags
0x180011563  mov     rcx, rax; hHeap
0x180011566  call    cs:__imp_HeapFree
0x18001156d  nop     dword ptr [rax+rax+00h]
0x180011572  mov     eax, ebx
0x180011574  mov     rbx, [rsp+88h+arg_0]
0x18001157c  add     rsp, 50h
0x180011580  pop     r15
0x180011582  pop     r14
0x180011584  pop     r13
0x180011586  pop     r12
0x180011588  pop     rdi
0x180011589  pop     rsi
0x18001158a  pop     rbp
0x18001158b  retn
```
