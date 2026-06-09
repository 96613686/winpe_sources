# CToolBar32::GetToolbarString(int,ushort * *)

- ea: `0x180005454`
- end: `0x18000569e`
- name: `?GetToolbarString@CToolBar32@@AEAAJHPEAPEAG@Z`
- size: `586`
- prototype: `__int64 __fastcall(CToolBar32 *__hidden this, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001a7c0`
- `0x180044500`

## callees

- `0x180005454`
- `0x1800056a4`
- `0x1800065b4`
- `0x180007700`
- `0x18000771c`
- `0x18001e4c0`
- `0x180043638`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180005613`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180005613`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800055af`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800055af`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180005551`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180005551`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005562`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005562`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000566c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000566c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000557a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000557a`

## pseudocode

```c
int __fastcall CToolBar32::GetToolbarString(HWND *this, int a2, unsigned __int16 **a3)
{
  HWND v5; // r8
  int result; // eax
  unsigned int v7; // r8d
  __int64 v8; // r14
  unsigned __int64 v9; // rbx
  void *ProcessHandleFromHwnd; // rax
  void *v11; // rdi
  SIZE_T v12; // r12
  void *v13; // r15
  _WORD *v14; // rbx
  int v15; // esi
  int Buffer; // [rsp+40h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v18; // [rsp+50h] [rbp-30h] BYREF
  _TBBUTTON v19; // [rsp+58h] [rbp-28h] BYREF

  *a3 = 0;
  Buffer = 0;
  v18 = 0;
  memset(&v19, 0, sizeof(v19));
  if ( !(unsigned int)CToolBar32::GetItemData((CToolBar32 *)this, a2, &v19) || (v19.fsStyle & 1) != 0 )
    return 1;
  v5 = this[10];
  v17 = 0;
  result = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, v5, 0x44Bu, v19.idCommand, 0, &v17);
  if ( result < 0 )
    return result;
  v8 = (int)v17;
  if ( (unsigned int)(v17 + 1) <= 1 )
  {
    if ( !CToolBar32::GetTooltipStringForControl((CToolBar32 *)this, this[10], v7, v19.idCommand, &v18) )
      return 1;
    v14 = v18;
  }
  else
  {
    if ( (int)v17 < 0 )
      return -2147024362;
    if ( (int)v17 + 1 < (unsigned int)v17 )
      return -2147024362;
    v9 = 2LL * (unsigned int)(v17 + 1);
    if ( v9 > 0xFFFFFFFF )
      return -2147024362;
    ProcessHandleFromHwnd = (void *)GetProcessHandleFromHwnd(this[10]);
    v11 = ProcessHandleFromHwnd;
    if ( !ProcessHandleFromHwnd )
      return -2147024882;
    v12 = (unsigned int)v9;
    v13 = VirtualAllocEx(ProcessHandleFromHwnd, 0, (unsigned int)v9, 0x1000u, 4u);
    if ( !v13 )
    {
      CloseHandle(v11);
      return -2147024882;
    }
    v14 = LocalAlloc(0x40u, (unsigned int)v9);
    if ( !v14 )
    {
      v15 = -2147024882;
LABEL_16:
      SharedFree(v13, v11);
      return v15;
    }
    Buffer = 0;
    WriteProcessMemory(v11, v13, &Buffer, 4u, 0);
    v15 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x44Bu, v19.idCommand, (__int64)v13, 0);
    if ( v15 < 0 )
    {
      LocalFree(v14);
      goto LABEL_16;
    }
    ReadProcessMemory(v11, v13, v14, v12, 0);
    SharedFree(v13, v11);
    v14[v8] = 0;
  }
  if ( v14 )
  {
    if ( *v14 )
    {
      *a3 = v14;
      return 0;
    }
    LocalFree(v14);
  }
  return 1;
}

```

## disassembly

```asm
0x180005454  mov     [rsp-38h+arg_18], rbx
0x180005459  push    rbp
0x18000545a  push    rsi
0x18000545b  push    rdi
0x18000545c  push    r12
0x18000545e  push    r13
0x180005460  push    r14
0x180005462  push    r15
0x180005464  mov     rbp, rsp
0x180005467  sub     rsp, 80h
0x18000546e  mov     rax, cs:__security_cookie
0x180005475  xor     rax, rsp
0x180005478  mov     [rbp+var_8], rax
0x18000547c  xor     r15d, r15d
0x18000547f  xorps   xmm0, xmm0
0x180005482  mov     [r8], r15
0x180005485  mov     r13, r8
0x180005488  lea     r8, [rbp+var_28]; struct _TBBUTTON *
0x18000548c  mov     [rbp+Buffer], r15d
0x180005490  mov     rsi, rcx
0x180005493  mov     [rbp+var_30], r15
0x180005497  movups  xmmword ptr [rbp+var_28.iBitmap], xmm0
0x18000549b  movups  xmmword ptr [rbp+var_28.dwData], xmm0
0x18000549f  call    ?GetItemData@CToolBar32@@QEAAHHPEAU_TBBUTTON@@@Z
0x1800054a4  test    eax, eax
0x1800054a6  jz      loc_180005672
0x1800054ac  test    [rbp+var_28.fsStyle], 1
0x1800054b0  jnz     loc_180005672
0x1800054b6  movsxd  rax, [rbp+var_28.idCommand]
0x1800054ba  lea     rcx, [rbp+var_38]
0x1800054be  mov     r8, [rsi+50h]; HWND
0x1800054c2  mov     r9d, 44Bh; unsigned int
0x1800054c8  mov     [rsp+80h+var_50], rcx; __int64 *
0x1800054cd  xor     edx, edx; bool
0x1800054cf  mov     [rsp+80h+var_58], r15; __int64
0x1800054d4  mov     rcx, rsi; this
0x1800054d7  mov     qword ptr [rsp+80h+flProtect], rax; unsigned __int64
0x1800054dc  mov     [rbp+var_38], r15
0x1800054e0  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z
0x1800054e5  test    eax, eax
0x1800054e7  js      loc_180005677
0x1800054ed  movsxd  r14, dword ptr [rbp+var_38]
0x1800054f1  lea     eax, [r14+1]
0x1800054f5  cmp     eax, 1
0x1800054f8  jbe     loc_180005635
0x1800054fe  test    r14d, r14d
0x180005501  js      loc_18000562E
0x180005507  lea     eax, [r14+1]
0x18000550b  cmp     eax, r14d
0x18000550e  jb      loc_18000562E
0x180005514  mov     ebx, eax
0x180005516  mov     eax, 0FFFFFFFFh
0x18000551b  add     rbx, rbx
0x18000551e  cmp     rbx, rax
0x180005521  ja      loc_18000562E
0x180005527  mov     rcx, [rsi+50h]
0x18000552b  call    GetProcessHandleFromHwnd
0x180005530  mov     rdi, rax
0x180005533  test    rax, rax
0x180005536  jz      short loc_180005568
0x180005538  mov     r9d, 1000h; flAllocationType
0x18000553e  mov     r8d, ebx; dwSize
0x180005541  xor     edx, edx; lpAddress
0x180005543  mov     r12d, ebx
0x180005546  mov     rcx, rax; hProcess
0x180005549  mov     [rsp+80h+flProtect], 4; flProtect
0x180005551  call    cs:__imp_VirtualAllocEx
0x180005557  mov     r15, rax
0x18000555a  test    rax, rax
0x18000555d  jnz     short loc_180005572
0x18000555f  mov     rcx, rdi; hObject
0x180005562  call    cs:__imp_CloseHandle
0x180005568  mov     eax, 8007000Eh
0x18000556d  jmp     loc_180005677
0x180005572  mov     rdx, r12; uBytes
0x180005575  mov     ecx, 40h ; '@'; uFlags
0x18000557a  call    cs:__imp_LocalAlloc
0x180005580  mov     rbx, rax
0x180005583  test    rax, rax
0x180005586  jnz     short loc_18000558F
0x180005588  mov     esi, 8007000Eh
0x18000558d  jmp     short loc_1800055EF
0x18000558f  mov     r9d, 4; nSize
0x180005595  mov     [rbp+Buffer], 0
0x18000559c  lea     r8, [rbp+Buffer]; lpBuffer
0x1800055a0  mov     qword ptr [rsp+80h+flProtect], 0; lpNumberOfBytesWritten
0x1800055a9  mov     rdx, r15; lpBaseAddress
0x1800055ac  mov     rcx, rdi; hProcess
0x1800055af  call    cs:__imp_WriteProcessMemory
0x1800055b5  movsxd  rax, [rbp+var_28.idCommand]
0x1800055b9  mov     r9d, 44Bh; unsigned int
0x1800055bf  mov     r8, [rsi+50h]; HWND
0x1800055c3  xor     edx, edx; bool
0x1800055c5  mov     [rsp+80h+var_50], 0; __int64 *
0x1800055ce  mov     rcx, rsi; this
0x1800055d1  mov     [rsp+80h+var_58], r15; __int64
0x1800055d6  mov     qword ptr [rsp+80h+flProtect], rax; unsigned __int64
0x1800055db  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z
0x1800055e0  mov     esi, eax
0x1800055e2  test    eax, eax
0x1800055e4  jns     short loc_1800055FE
0x1800055e6  mov     rcx, rbx; hMem
0x1800055e9  call    cs:__imp_LocalFree
0x1800055ef  mov     rdx, rdi; hProcess
0x1800055f2  mov     rcx, r15; lpAddress
0x1800055f5  call    ?SharedFree@@YAXPEAX0@Z
0x1800055fa  mov     eax, esi
0x1800055fc  jmp     short loc_180005677
0x1800055fe  mov     r9, r12; nSize
0x180005601  mov     qword ptr [rsp+80h+flProtect], 0; lpNumberOfBytesRead
0x18000560a  mov     r8, rbx; lpBuffer
0x18000560d  mov     rdx, r15; lpBaseAddress
0x180005610  mov     rcx, rdi; hProcess
0x180005613  call    cs:__imp_ReadProcessMemory
0x180005619  mov     rdx, rdi; hProcess
0x18000561c  mov     rcx, r15; lpAddress
0x18000561f  call    ?SharedFree@@YAXPEAX0@Z
0x180005624  xor     r15d, r15d
0x180005627  mov     [rbx+r14*2], r15w
0x18000562c  jmp     short loc_180005656
0x18000562e  mov     eax, 80070216h
0x180005633  jmp     short loc_180005677
0x180005635  mov     r9d, [rbp+var_28.idCommand]; unsigned int
0x180005639  lea     rax, [rbp+var_30]
0x18000563d  mov     rdx, [rsi+50h]; HWND
0x180005641  mov     rcx, rsi; this
0x180005644  mov     qword ptr [rsp+80h+flProtect], rax; unsigned __int16 **
0x180005649  call    ?GetTooltipStringForControl@CToolBar32@@AEAAHPEAUHWND__@@IKPEAPEAG@Z
0x18000564e  test    eax, eax
0x180005650  jz      short loc_180005672
0x180005652  mov     rbx, [rbp+var_30]
0x180005656  test    rbx, rbx
0x180005659  jz      short loc_180005672
0x18000565b  cmp     [rbx], r15w
0x18000565f  jz      short loc_180005669
0x180005661  mov     [r13+0], rbx
0x180005665  xor     eax, eax
0x180005667  jmp     short loc_180005677
0x180005669  mov     rcx, rbx; hMem
0x18000566c  call    cs:__imp_LocalFree
0x180005672  mov     eax, 1
0x180005677  mov     rcx, [rbp+var_8]
0x18000567b  xor     rcx, rsp; StackCookie
0x18000567e  call    __security_check_cookie
0x180005683  mov     rbx, [rsp+80h+arg_18]
0x18000568b  add     rsp, 80h
0x180005692  pop     r15
0x180005694  pop     r14
0x180005696  pop     r13
0x180005698  pop     r12
0x18000569a  pop     rdi
0x18000569b  pop     rsi
0x18000569c  pop     rbp
0x18000569d  retn
```
