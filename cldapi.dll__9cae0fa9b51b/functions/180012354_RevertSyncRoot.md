# RevertSyncRoot

- ea: `0x180012354`
- end: `0x18001261c`
- name: `RevertSyncRoot`
- size: `712`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007f30`
- `0x18000bb90`

## callees

- `0x18000231e`
- `0x180012354`
- `0x18001cd74`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180012494`
- `ntdll!RtlNtStatusToDosError` at `0x18001250f`
- `ntdll!RtlNtStatusToDosError` at `0x18001257e`
- `ntdll!RtlNtStatusToDosError` at `0x180012494`
- `ntdll!RtlNtStatusToDosError` at `0x18001250f`
- `ntdll!RtlNtStatusToDosError` at `0x18001257e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800125df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800125df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800125f3`
- `FLTLIB!FilterSendMessage` at `0x1800125cc`
- `FLTLIB!FilterSendMessage` at `0x1800125cc`

## pseudocode

```c
int __fastcall RevertSyncRoot(unsigned __int64 hFile)
{
  HANDLE ProcessHeap; // rax
  _DWORD *v3; // rax
  _DWORD *v4; // rbx
  int v5; // edx
  NTSTATUS v6; // edi
  NTSTATUS v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // ecx
  signed int v11; // eax
  bool v12; // sf
  NTSTATUS v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rax
  signed int v16; // eax
  bool v17; // sf
  __int64 v18; // rcx
  __int64 v19; // rax
  signed int v20; // eax
  bool v21; // sf
  HANDLE v22; // rax
  _DWORD v24[3]; // [rsp+40h] [rbp-C8h] BYREF
  char v25[148]; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD BytesReturned; // [rsp+118h] [rbp+10h] BYREF

  memset_0(v25, 0, 0x8Cu);
  v24[0] = -1879048166;
  BytesReturned = 0;
  v24[1] = -1073741801;
  v24[2] = 0;
  IssueHsmControl(hFile, v24, 0x98u, 0, 0, &BytesReturned, 0);
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 8u, 0xD8u);
  v4 = v3;
  v5 = v3 == 0 ? 8 : 0;
  if ( !v3 )
    v5 |= 0x80070000;
  if ( v5 >= 0 )
  {
    *(_QWORD *)v3 = 1886219331;
    v3[2] = 200;
    v3[3] = 1507328;
    memset_0(v3 + 4, 0, 0xB8u);
    v6 = -1073741811;
    if ( *((_WORD *)v4 + 7) )
    {
      v8 = (unsigned int)v4[2];
      if ( ((v8 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xD8 )
      {
        v10 = (v8 + 3) & 0xFFFFFFFC;
        v9 = v10;
        v4[2] = v10;
        v4[5] = v10;
        v7 = 0;
        v4[4] = 65543;
        *((_BYTE *)v4 + v9) = 1;
        ++v4[2];
      }
      else
      {
        v7 = -1073741789;
      }
    }
    else
    {
      v7 = -1073741811;
    }
    v11 = RtlNtStatusToDosError(v7);
    v12 = v11 < 0;
    if ( v11 > 0 )
      v12 = 1;
    if ( !v12 )
    {
      if ( *((_WORD *)v4 + 7) > 1u )
      {
        v14 = (unsigned int)v4[2];
        if ( ((v14 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xD8 )
        {
          v15 = ((_DWORD)v14 + 3) & 0xFFFFFFFC;
          v4[2] = v15;
          if ( *((_WORD *)v4 + 12) )
            *((_WORD *)v4 + 6) |= 1u;
          v4[6] = 131080;
          v13 = 0;
          v4[7] = v15;
          *(_WORD *)((char *)v4 + v15) = 3;
          v4[2] += 2;
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
      v17 = v16 < 0;
      if ( v16 > 0 )
        v17 = 1;
      if ( !v17 )
      {
        if ( *((_WORD *)v4 + 7) > 2u )
        {
          v18 = (unsigned int)v4[2];
          if ( ((v18 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xD8 )
          {
            v19 = ((_DWORD)v18 + 3) & 0xFFFFFFFC;
            v4[2] = v19;
            if ( *((_WORD *)v4 + 16) )
              *((_WORD *)v4 + 6) |= 1u;
            v4[8] = 524299;
            v6 = 0;
            v4[9] = v19;
            *(_QWORD *)((char *)v4 + v19) = hFile;
            v4[2] += 8;
          }
          else
          {
            v6 = -1073741789;
          }
        }
        v20 = RtlNtStatusToDosError(v6);
        v21 = v20 < 0;
        if ( v20 > 0 )
          v21 = 1;
        if ( !v21 )
        {
          v4[1] = 0;
          *((_WORD *)v4 + 6) &= ~2u;
          FilterSendMessage(hPort, v4, 0xD8u, 0, 0, &BytesReturned);
        }
      }
    }
    goto LABEL_33;
  }
  if ( v3 )
  {
LABEL_33:
    v22 = GetProcessHeap();
    LODWORD(v3) = HeapFree(v22, 0, v4);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x180012354  mov     [rsp+arg_0], rbx
0x180012359  mov     [rsp+arg_10], rbp
0x18001235e  push    rsi
0x18001235f  push    rdi
0x180012360  push    r12
0x180012362  push    r14
0x180012364  push    r15
0x180012366  sub     rsp, 0E0h
0x18001236d  mov     rbp, rcx
0x180012370  xor     edx, edx; Val
0x180012372  lea     rcx, [rsp+108h+var_BC]; void *
0x180012377  mov     r8d, 8Ch; Size
0x18001237d  call    memset_0
0x180012382  xor     r14d, r14d
0x180012385  mov     [rsp+108h+var_C8], 9000001Ah
0x18001238d  lea     rax, [rsp+108h+BytesReturned]
0x180012395  mov     [rsp+108h+var_D8], r14; __int64
0x18001239a  mov     [rsp+108h+lpBytesReturned], rax; lpNumberOfBytesTransferred
0x18001239f  lea     rdx, [rsp+108h+var_C8]
0x1800123a4  xor     r9d, r9d
0x1800123a7  mov     [rsp+108h+dwOutBufferSize], r14d; DWORD
0x1800123ac  mov     r8d, 98h
0x1800123b2  mov     [rsp+108h+BytesReturned], r14d
0x1800123ba  mov     rcx, rbp; hFile
0x1800123bd  mov     [rsp+108h+var_C4], 0C0000017h
0x1800123c5  mov     [rsp+108h+var_C0], r14d
0x1800123ca  call    IssueHsmControl
0x1800123cf  call    cs:__imp_GetProcessHeap
0x1800123d6  nop     dword ptr [rax+rax+00h]
0x1800123db  lea     r12d, [r14+8]
0x1800123df  mov     r8d, 0D8h; dwBytes
0x1800123e5  mov     rcx, rax; hHeap
0x1800123e8  mov     edx, r12d; dwFlags
0x1800123eb  call    cs:__imp_HeapAlloc
0x1800123f2  nop     dword ptr [rax+rax+00h]
0x1800123f7  mov     rcx, rax
0x1800123fa  mov     rbx, rax
0x1800123fd  neg     rcx
0x180012400  sbb     edx, edx
0x180012402  not     edx
0x180012404  and     edx, r12d
0x180012407  mov     ecx, edx
0x180012409  or      ecx, 80070000h
0x18001240f  test    rax, rax
0x180012412  cmovz   edx, ecx
0x180012415  test    edx, edx
0x180012417  js      loc_1800125DA
0x18001241d  xor     edx, edx; Val
0x18001241f  mov     qword ptr [rax], 706D6C43h
0x180012426  mov     r8d, 0B8h; Size
0x18001242c  mov     dword ptr [rax+8], 0C8h
0x180012433  lea     rcx, [rax+10h]; void *
0x180012437  mov     dword ptr [rax+0Ch], 170000h
0x18001243e  call    memset_0
0x180012443  lea     r15d, [r14+1]
0x180012447  mov     edi, 0C000000Dh
0x18001244c  cmp     r14w, [rbx+0Eh]
0x180012451  jb      short loc_180012457
0x180012453  mov     ecx, edi
0x180012455  jmp     short loc_180012494
0x180012457  mov     ecx, [rbx+8]
0x18001245a  lea     rax, [rcx+3]
0x18001245e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180012462  add     rax, r15
0x180012465  cmp     rax, 0D8h
0x18001246b  jbe     short loc_180012474
0x18001246d  mov     ecx, 0C0000023h
0x180012472  jmp     short loc_180012494
0x180012474  lea     eax, [rcx+3]
0x180012477  and     eax, 0FFFFFFFCh
0x18001247a  mov     ecx, eax
0x18001247c  mov     [rbx+8], ecx
0x18001247f  mov     [rbx+14h], ecx
0x180012482  mov     ecx, r14d; Status
0x180012485  mov     dword ptr [rbx+10h], 10007h
0x18001248c  mov     [rax+rbx], r15b
0x180012490  add     [rbx+8], r15d
0x180012494  call    cs:__imp_RtlNtStatusToDosError
0x18001249b  nop     dword ptr [rax+rax+00h]
0x1800124a0  test    eax, eax
0x1800124a2  jle     short loc_1800124AE
0x1800124a4  movzx   eax, ax
0x1800124a7  or      eax, 80070000h
0x1800124ac  test    eax, eax
0x1800124ae  js      loc_1800125DF
0x1800124b4  mov     esi, 2
0x1800124b9  cmp     r15w, [rbx+0Eh]
0x1800124be  jb      short loc_1800124C4
0x1800124c0  mov     ecx, edi
0x1800124c2  jmp     short loc_18001250F
0x1800124c4  mov     ecx, [rbx+8]
0x1800124c7  mov     edx, 3
0x1800124cc  lea     rax, [rdx+rcx]
0x1800124d0  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800124d4  add     rax, rsi
0x1800124d7  cmp     rax, 0D8h
0x1800124dd  jbe     short loc_1800124E6
0x1800124df  mov     ecx, 0C0000023h
0x1800124e4  jmp     short loc_18001250F
0x1800124e6  lea     eax, [rcx+3]
0x1800124e9  and     eax, 0FFFFFFFCh
0x1800124ec  mov     [rbx+8], eax
0x1800124ef  cmp     [rbx+18h], r14w
0x1800124f4  jz      short loc_1800124FB
0x1800124f6  or      [rbx+0Ch], r15w
0x1800124fb  mov     dword ptr [rbx+18h], 20008h
0x180012502  mov     ecx, r14d; Status
0x180012505  mov     [rbx+1Ch], eax
0x180012508  mov     [rax+rbx], dx
0x18001250c  add     [rbx+8], esi
0x18001250f  call    cs:__imp_RtlNtStatusToDosError
0x180012516  nop     dword ptr [rax+rax+00h]
0x18001251b  test    eax, eax
0x18001251d  jle     short loc_180012529
0x18001251f  movzx   eax, ax
0x180012522  or      eax, 80070000h
0x180012527  test    eax, eax
0x180012529  js      loc_1800125DF
0x18001252f  cmp     si, [rbx+0Eh]
0x180012533  jnb     short loc_18001257C
0x180012535  mov     ecx, [rbx+8]
0x180012538  lea     rax, [rcx+3]
0x18001253c  and     rax, 0FFFFFFFFFFFFFFFCh
0x180012540  add     rax, r12
0x180012543  cmp     rax, 0D8h
0x180012549  jbe     short loc_180012552
0x18001254b  mov     edi, 0C0000023h
0x180012550  jmp     short loc_18001257C
0x180012552  lea     eax, [rcx+3]
0x180012555  and     eax, 0FFFFFFFCh
0x180012558  mov     [rbx+8], eax
0x18001255b  cmp     [rbx+20h], r14w
0x180012560  jz      short loc_180012567
0x180012562  or      [rbx+0Ch], r15w
0x180012567  mov     dword ptr [rbx+20h], 8000Bh
0x18001256e  mov     edi, r14d
0x180012571  mov     [rbx+24h], eax
0x180012574  mov     [rax+rbx], rbp
0x180012578  add     [rbx+8], r12d
0x18001257c  mov     ecx, edi; Status
0x18001257e  call    cs:__imp_RtlNtStatusToDosError
0x180012585  nop     dword ptr [rax+rax+00h]
0x18001258a  test    eax, eax
0x18001258c  jle     short loc_180012598
0x18001258e  movzx   eax, ax
0x180012591  or      eax, 80070000h
0x180012596  test    eax, eax
0x180012598  js      short loc_1800125DF
0x18001259a  mov     eax, 0FFFDh
0x18001259f  mov     [rbx+4], r14d
0x1800125a3  and     [rbx+0Ch], ax
0x1800125a7  xor     r9d, r9d; lpOutBuffer
0x1800125aa  mov     rcx, qword ptr cs:hPort; hPort
0x1800125b1  lea     rax, [rsp+108h+BytesReturned]
0x1800125b9  mov     [rsp+108h+lpBytesReturned], rax; lpBytesReturned
0x1800125be  mov     r8d, 0D8h; dwInBufferSize
0x1800125c4  mov     rdx, rbx; lpInBuffer
0x1800125c7  mov     [rsp+108h+dwOutBufferSize], r14d; dwOutBufferSize
0x1800125cc  call    cs:__imp_FilterSendMessage
0x1800125d3  nop     dword ptr [rax+rax+00h]
0x1800125d8  jmp     short loc_1800125DF
0x1800125da  test    rbx, rbx
0x1800125dd  jz      short loc_1800125FF
0x1800125df  call    cs:__imp_GetProcessHeap
0x1800125e6  nop     dword ptr [rax+rax+00h]
0x1800125eb  mov     r8, rbx; lpMem
0x1800125ee  xor     edx, edx; dwFlags
0x1800125f0  mov     rcx, rax; hHeap
0x1800125f3  call    cs:__imp_HeapFree
0x1800125fa  nop     dword ptr [rax+rax+00h]
0x1800125ff  lea     r11, [rsp+108h+var_28]
0x180012607  mov     rbx, [r11+30h]
0x18001260b  mov     rbp, [r11+40h]
0x18001260f  mov     rsp, r11
0x180012612  pop     r15
0x180012614  pop     r14
0x180012616  pop     r12
0x180012618  pop     rdi
0x180012619  pop     rsi
0x18001261a  retn
```
