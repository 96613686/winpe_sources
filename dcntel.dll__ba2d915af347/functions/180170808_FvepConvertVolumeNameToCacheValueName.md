# FvepConvertVolumeNameToCacheValueName

- ea: `0x180170808`
- end: `0x180170c1e`
- name: `FvepConvertVolumeNameToCacheValueName`
- size: `1046`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180170f20`
- `0x180171220`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18003d5c0`
- `0x180170808`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801708f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180170a99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180170b15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801708f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180170a99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180170b15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801708e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170a8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170bde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801708e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170a8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170ba5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180170bde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170a6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170bb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170bec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170a6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170bb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180170bec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801709ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180170a2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801709ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180170a2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180170b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180170b91`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801709b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801709b9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180170a1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180170ad4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180170a1b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180170ad4`

## pseudocode

```c
__int64 __fastcall FvepConvertVolumeNameToCacheValueName(WCHAR *a1, wchar_t **a2)
{
  DWORD v4; // r13d
  wchar_t *v5; // r12
  signed int v6; // ebx
  WCHAR *v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rax
  SIZE_T v11; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v13; // rax
  const WCHAR *v14; // r10
  unsigned __int64 v15; // rdi
  _WORD *v16; // r14
  __int64 v17; // rax
  WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  unsigned __int64 v20; // r15
  HANDLE FileW; // rax
  signed int LastError; // eax
  HANDLE v23; // rdi
  signed int v24; // eax
  HANDLE v25; // rax
  HANDLE v26; // rax
  unsigned __int64 v27; // rax
  SIZE_T v28; // rdi
  HANDLE v29; // rax
  SIZE_T v30; // rsi
  HANDLE v31; // rax
  HANDLE v32; // rax
  HANDLE v33; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  wchar_t **v38; // [rsp+58h] [rbp-A8h]
  _BYTE OutBuffer[272]; // [rsp+70h] [rbp-90h] BYREF

  v38 = a2;
  v4 = 260;
  memset_0(OutBuffer, 0, 0x104u);
  v5 = 0;
  BytesReturned = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v7 = a1;
      v8 = 0x7FFFFFFF;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v8;
      }
      while ( v8 );
      v6 = -2147024809;
      v9 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
      if ( v8 )
      {
        lpMem = 0;
        v10 = 2 * v9;
        if ( is_mul_ok(v9, 2u) && (v11 = v10 + 2, v10 + 2 >= v10) )
        {
          ProcessHeap = GetProcessHeap();
          v13 = HeapAlloc(ProcessHeap, 8u, v11);
          lpMem = v13;
          v14 = v13;
          if ( v13 )
          {
            v15 = v11 >> 1;
            v16 = OutBuffer;
            if ( v15 )
            {
              if ( v15 <= 0x7FFFFFFF )
              {
                v17 = 2147483646;
                v18 = (WCHAR *)v14;
                do
                {
                  if ( !v17 )
                    break;
                  if ( !*a1 )
                    break;
                  *v18++ = *a1++;
                  --v17;
                  --v15;
                }
                while ( v15 );
                v19 = v18 - 1;
                v20 = 0;
                v6 = v15 == 0 ? 0x8007007A : 0;
                if ( v15 )
                  v19 = v18;
                *v19 = 0;
                if ( v15 )
                {
                  if ( v9 && v14[v9 - 1] == 92 )
                    v14[v9 - 1] = 0;
                  FileW = CreateFileW(v14, 0, 7u, 0, 3u, 0, 0);
                  hDevice = FileW;
                  if ( FileW == (HANDLE)-1LL )
                  {
                    LastError = GetLastError();
                    v6 = LastError;
                    if ( LastError > 0 )
                      v6 = (unsigned __int16)LastError | 0x80070000;
                  }
                  else
                  {
                    BytesReturned = 0;
                    if ( DeviceIoControl(FileW, 0x4D0000u, 0, 0, OutBuffer, 0x104u, &BytesReturned, 0) )
                    {
LABEL_41:
                      v27 = 4LL * (unsigned __int16)*v16;
                      if ( is_mul_ok((unsigned __int16)*v16, 4u) && (v28 = v27 + 2, v27 + 2 >= v27) )
                      {
                        v29 = GetProcessHeap();
                        v5 = (wchar_t *)HeapAlloc(v29, 8u, v28);
                        if ( v5 )
                        {
                          v30 = 0;
                          v6 = 0;
                          if ( *v16 )
                          {
                            do
                            {
                              if ( v30 >= v28 >> 1 )
                                break;
                              v6 = StringCbPrintfW(
                                     &v5[v30],
                                     v28 - 2 * v30,
                                     L"%02X",
                                     *((unsigned __int8 *)v16 + v20 + 2));
                              if ( v6 < 0 )
                                goto LABEL_51;
                              ++v20;
                              v30 += 2LL;
                            }
                            while ( v20 < (unsigned __int16)*v16 );
                          }
                          *v38 = v5;
                          v5 = 0;
                        }
                        else
                        {
LABEL_49:
                          v6 = -2147024882;
                        }
                      }
                      else
                      {
LABEL_50:
                        v6 = -2147024362;
                      }
                    }
                    else
                    {
                      v23 = hDevice;
                      while ( 1 )
                      {
                        v24 = GetLastError();
                        v6 = v24;
                        if ( v24 > 0 )
                          v6 = (unsigned __int16)v24 | 0x80070000;
                        if ( v6 != -2147024774 && v6 != -2147024662 )
                          break;
                        if ( v16 != (_WORD *)OutBuffer )
                        {
                          v25 = GetProcessHeap();
                          HeapFree(v25, 0, v16);
                          v16 = 0;
                        }
                        if ( v4 + 260 < v4 )
                          goto LABEL_50;
                        v4 += 260;
                        v26 = GetProcessHeap();
                        v16 = HeapAlloc(v26, 0, v4);
                        if ( !v16 )
                          goto LABEL_49;
                        BytesReturned = 0;
                        if ( DeviceIoControl(v23, 0x4D0000u, 0, 0, v16, v4, &BytesReturned, 0) )
                          goto LABEL_41;
                      }
                    }
LABEL_51:
                    CloseHandle(hDevice);
                  }
                }
              }
              else
              {
                *v13 = 0;
              }
            }
            v31 = GetProcessHeap();
            HeapFree(v31, 0, lpMem);
            if ( v5 )
            {
              v32 = GetProcessHeap();
              HeapFree(v32, 0, v5);
            }
            if ( v16 != (_WORD *)OutBuffer )
            {
              v33 = GetProcessHeap();
              HeapFree(v33, 0, v16);
            }
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
        else
        {
          return (unsigned int)-2147024362;
        }
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180170808  push    rbp
0x18017080a  push    rbx
0x18017080b  push    rsi
0x18017080c  push    rdi
0x18017080d  push    r12
0x18017080f  push    r13
0x180170811  push    r14
0x180170813  push    r15
0x180170815  lea     rbp, [rsp-98h]
0x18017081d  sub     rsp, 198h
0x180170824  mov     rax, cs:__security_cookie
0x18017082b  xor     rax, rsp
0x18017082e  mov     [rbp+0D0h+var_50], rax
0x180170835  mov     rbx, rdx
0x180170838  mov     [rsp+1D0h+var_178], rdx
0x18017083d  mov     r15, rcx
0x180170840  mov     r13d, 104h
0x180170846  mov     r8d, r13d; Size
0x180170849  lea     rcx, [rsp+1D0h+OutBuffer]; void *
0x18017084e  xor     edx, edx; Val
0x180170850  call    memset_0
0x180170855  xor     r12d, r12d
0x180170858  mov     [rsp+1D0h+BytesReturned], r12d
0x18017085d  test    r15, r15
0x180170860  jnz     short loc_18017086C
0x180170862  mov     ebx, 80070057h
0x180170867  jmp     loc_180170BF9
0x18017086c  test    rbx, rbx
0x18017086f  jnz     short loc_18017087B
0x180170871  mov     ebx, 80004003h
0x180170876  jmp     loc_180170BF9
0x18017087b  mov     ecx, 7FFFFFFFh
0x180170880  mov     rax, r15
0x180170883  mov     edx, ecx
0x180170885  cmp     [rax], r12w
0x180170889  jz      short loc_180170895
0x18017088b  add     rax, 2
0x18017088f  sub     rdx, 1
0x180170893  jnz     short loc_180170885
0x180170895  mov     rax, rdx
0x180170898  mov     ebx, 80070057h
0x18017089d  neg     rax
0x1801708a0  mov     rax, rdx
0x1801708a3  sbb     r8d, r8d
0x1801708a6  sub     rcx, rdx
0x1801708a9  not     r8d
0x1801708ac  and     r8d, ebx
0x1801708af  neg     rax
0x1801708b2  sbb     rsi, rsi
0x1801708b5  and     rsi, rcx
0x1801708b8  test    rdx, rdx
0x1801708bb  jnz     short loc_1801708C5
0x1801708bd  mov     ebx, r8d
0x1801708c0  jmp     loc_180170BF9
0x1801708c5  mov     eax, 2
0x1801708ca  mov     [rsp+1D0h+lpMem], r12
0x1801708cf  mul     rsi
0x1801708d2  test    rdx, rdx
0x1801708d5  jnz     loc_180170BF4
0x1801708db  lea     rdi, [rax+2]
0x1801708df  cmp     rdi, rax
0x1801708e2  jb      loc_180170BF4
0x1801708e8  call    cs:__imp_GetProcessHeap
0x1801708ee  mov     r8, rdi; dwBytes
0x1801708f1  mov     edx, 8; dwFlags
0x1801708f6  mov     rcx, rax; hHeap
0x1801708f9  call    cs:__imp_HeapAlloc
0x1801708ff  mov     [rsp+1D0h+lpMem], rax
0x180170904  mov     r10, rax
0x180170907  test    rax, rax
0x18017090a  jnz     short loc_180170916
0x18017090c  mov     ebx, 8007000Eh
0x180170911  jmp     loc_180170BF9
0x180170916  shr     rdi, 1
0x180170919  lea     r14, [rsp+1D0h+OutBuffer]
0x18017091e  jz      loc_180170B99
0x180170924  cmp     rdi, 7FFFFFFFh
0x18017092b  jbe     short loc_180170935
0x18017092d  xor     r15d, r15d
0x180170930  jmp     loc_180170BA1
0x180170935  mov     eax, 7FFFFFFEh
0x18017093a  mov     rdx, r10
0x18017093d  test    rax, rax
0x180170940  jz      short loc_18017095F
0x180170942  movzx   ecx, word ptr [r15]
0x180170946  test    cx, cx
0x180170949  jz      short loc_18017095F
0x18017094b  mov     [rdx], cx
0x18017094e  add     r15, 2
0x180170952  add     rdx, 2
0x180170956  dec     rax
0x180170959  sub     rdi, 1
0x18017095d  jnz     short loc_18017093D
0x18017095f  mov     rax, rdi
0x180170962  lea     rcx, [rdx-2]
0x180170966  neg     rax
0x180170969  sbb     ebx, ebx
0x18017096b  xor     r15d, r15d
0x18017096e  not     ebx
0x180170970  and     ebx, 8007007Ah
0x180170976  test    rdi, rdi
0x180170979  cmovnz  rcx, rdx
0x18017097d  mov     [rcx], r15w
0x180170981  jz      loc_180170BA5
0x180170987  test    rsi, rsi
0x18017098a  jz      short loc_18017099B
0x18017098c  cmp     word ptr [r10+rsi*2-2], 5Ch ; '\'
0x180170993  jnz     short loc_18017099B
0x180170995  mov     [r10+rsi*2-2], r15w
0x18017099b  xor     r9d, r9d; lpSecurityAttributes
0x18017099e  mov     [rsp+1D0h+hTemplateFile], r15; hTemplateFile
0x1801709a3  mov     [rsp+1D0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1801709a8  xor     edx, edx; dwDesiredAccess
0x1801709aa  mov     rcx, r10; lpFileName
0x1801709ad  mov     [rsp+1D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1801709b5  lea     r8d, [r9+7]; dwShareMode
0x1801709b9  call    cs:__imp_CreateFileW
0x1801709bf  mov     [rsp+1D0h+hDevice], rax
0x1801709c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801709c8  jnz     short loc_1801709E8
0x1801709ca  call    cs:__imp_GetLastError
0x1801709d0  mov     ebx, eax
0x1801709d2  test    eax, eax
0x1801709d4  jle     loc_180170BA5
0x1801709da  movzx   ebx, ax
0x1801709dd  or      ebx, 80070000h
0x1801709e3  jmp     loc_180170BA5
0x1801709e8  mov     [rsp+1D0h+lpOverlapped], r15; lpOverlapped
0x1801709ed  lea     rcx, [rsp+1D0h+BytesReturned]
0x1801709f2  mov     [rsp+1D0h+hTemplateFile], rcx; lpBytesReturned
0x1801709f7  mov     esi, 4D0000h
0x1801709fc  lea     rcx, [rsp+1D0h+OutBuffer]
0x180170a01  mov     [rsp+1D0h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x180170a06  mov     qword ptr [rsp+1D0h+dwCreationDisposition], rcx; lpOutBuffer
0x180170a0b  xor     r9d, r9d; nInBufferSize
0x180170a0e  mov     rcx, rax; hDevice
0x180170a11  mov     [rsp+1D0h+BytesReturned], r15d
0x180170a16  xor     r8d, r8d; lpInBuffer
0x180170a19  mov     edx, esi; dwIoControlCode
0x180170a1b  call    cs:__imp_DeviceIoControl
0x180170a21  test    eax, eax
0x180170a23  jnz     loc_180170AE2
0x180170a29  mov     rdi, [rsp+1D0h+hDevice]
0x180170a2e  call    cs:__imp_GetLastError
0x180170a34  mov     ebx, eax
0x180170a36  test    eax, eax
0x180170a38  jle     short loc_180170A43
0x180170a3a  movzx   ebx, ax
0x180170a3d  or      ebx, 80070000h
0x180170a43  cmp     ebx, 8007007Ah
0x180170a49  jz      short loc_180170A57
0x180170a4b  cmp     ebx, 800700EAh
0x180170a51  jnz     loc_180170B8C
0x180170a57  lea     rax, [rsp+1D0h+OutBuffer]
0x180170a5c  cmp     r14, rax
0x180170a5f  jz      short loc_180170A78
0x180170a61  call    cs:__imp_GetProcessHeap
0x180170a67  mov     r8, r14; lpMem
0x180170a6a  xor     edx, edx; dwFlags
0x180170a6c  mov     rcx, rax; hHeap
0x180170a6f  call    cs:__imp_HeapFree
0x180170a75  mov     r14, r15
0x180170a78  lea     eax, [r13+104h]
0x180170a7f  cmp     eax, r13d
0x180170a82  jb      loc_180170B87
0x180170a88  mov     r13d, eax
0x180170a8b  call    cs:__imp_GetProcessHeap
0x180170a91  mov     r8d, r13d; dwBytes
0x180170a94  xor     edx, edx; dwFlags
0x180170a96  mov     rcx, rax; hHeap
0x180170a99  call    cs:__imp_HeapAlloc
0x180170a9f  mov     r14, rax
0x180170aa2  test    rax, rax
0x180170aa5  jz      loc_180170B80
0x180170aab  mov     [rsp+1D0h+lpOverlapped], r15; lpOverlapped
0x180170ab0  lea     rax, [rsp+1D0h+BytesReturned]
0x180170ab5  mov     [rsp+1D0h+hTemplateFile], rax; lpBytesReturned
0x180170aba  xor     r9d, r9d; nInBufferSize
0x180170abd  mov     [rsp+1D0h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x180170ac2  xor     r8d, r8d; lpInBuffer
0x180170ac5  mov     edx, esi; dwIoControlCode
0x180170ac7  mov     qword ptr [rsp+1D0h+dwCreationDisposition], r14; lpOutBuffer
0x180170acc  mov     rcx, rdi; hDevice
0x180170acf  mov     [rsp+1D0h+BytesReturned], r15d
0x180170ad4  call    cs:__imp_DeviceIoControl
0x180170ada  test    eax, eax
0x180170adc  jz      loc_180170A2E
0x180170ae2  movzx   ecx, word ptr [r14]
0x180170ae6  mov     eax, 4
0x180170aeb  mul     rcx
0x180170aee  test    rdx, rdx
0x180170af1  jnz     loc_180170B87
0x180170af7  lea     rdi, [rax+2]
0x180170afb  cmp     rdi, rax
0x180170afe  jb      loc_180170B87
0x180170b04  call    cs:__imp_GetProcessHeap
0x180170b0a  mov     r8, rdi; dwBytes
0x180170b0d  mov     edx, 8; dwFlags
0x180170b12  mov     rcx, rax; hHeap
0x180170b15  call    cs:__imp_HeapAlloc
0x180170b1b  mov     r12, rax
0x180170b1e  test    rax, rax
0x180170b21  jz      short loc_180170B80
0x180170b23  xor     eax, eax
0x180170b25  mov     esi, eax
0x180170b27  mov     ebx, eax
0x180170b29  cmp     ax, [r14]
0x180170b2d  jnb     short loc_180170B70
0x180170b2f  mov     r13, rdi
0x180170b32  shr     r13, 1
0x180170b35  cmp     rsi, r13
0x180170b38  jnb     short loc_180170B70
0x180170b3a  movzx   r9d, byte ptr [r14+r15+2]
0x180170b40  lea     rax, [rsi+rsi]
0x180170b44  mov     rdx, rdi
0x180170b47  lea     rcx, [rax+r12]; pszDest
0x180170b4b  sub     rdx, rax; cbDest
0x180170b4e  lea     r8, a02x; "%02X"
0x180170b55  call    StringCbPrintfW
0x180170b5a  mov     ebx, eax
0x180170b5c  test    eax, eax
0x180170b5e  js      short loc_180170B8C
0x180170b60  movzx   ecx, word ptr [r14]
0x180170b64  inc     r15
0x180170b67  add     rsi, 2
0x180170b6b  cmp     r15, rcx
0x180170b6e  jb      short loc_180170B35
0x180170b70  mov     rax, [rsp+1D0h+var_178]
0x180170b75  xor     r15d, r15d
0x180170b78  mov     [rax], r12
0x180170b7b  mov     r12d, r15d
0x180170b7e  jmp     short loc_180170B8C
0x180170b80  mov     ebx, 8007000Eh
0x180170b85  jmp     short loc_180170B8C
0x180170b87  mov     ebx, 80070216h
0x180170b8c  mov     rcx, [rsp+1D0h+hDevice]; hObject
0x180170b91  call    cs:__imp_CloseHandle
0x180170b97  jmp     short loc_180170BA5
0x180170b99  xor     r15d, r15d
0x180170b9c  test    rdi, rdi
0x180170b9f  jz      short loc_180170BA5
0x180170ba1  mov     [rax], r15w
0x180170ba5  call    cs:__imp_GetProcessHeap
0x180170bab  mov     r8, [rsp+1D0h+lpMem]; lpMem
0x180170bb0  xor     edx, edx; dwFlags
0x180170bb2  mov     rcx, rax; hHeap
0x180170bb5  call    cs:__imp_HeapFree
0x180170bbb  test    r12, r12
0x180170bbe  jz      short loc_180170BD4
0x180170bc0  call    cs:__imp_GetProcessHeap
0x180170bc6  mov     r8, r12; lpMem
0x180170bc9  xor     edx, edx; dwFlags
0x180170bcb  mov     rcx, rax; hHeap
0x180170bce  call    cs:__imp_HeapFree
0x180170bd4  lea     rax, [rsp+1D0h+OutBuffer]
0x180170bd9  cmp     r14, rax
0x180170bdc  jz      short loc_180170BF9
0x180170bde  call    cs:__imp_GetProcessHeap
0x180170be4  mov     r8, r14; lpMem
0x180170be7  xor     edx, edx; dwFlags
0x180170be9  mov     rcx, rax; hHeap
0x180170bec  call    cs:__imp_HeapFree
0x180170bf2  jmp     short loc_180170BF9
0x180170bf4  mov     ebx, 80070216h
0x180170bf9  mov     eax, ebx
0x180170bfb  mov     rcx, [rbp+0D0h+var_50]
0x180170c02  xor     rcx, rsp; StackCookie
0x180170c05  call    __security_check_cookie
0x180170c0a  add     rsp, 198h
0x180170c11  pop     r15
0x180170c13  pop     r14
0x180170c15  pop     r13
0x180170c17  pop     r12
0x180170c19  pop     rdi
0x180170c1a  pop     rsi
0x180170c1b  pop     rbx
0x180170c1c  pop     rbp
0x180170c1d  retn
```
