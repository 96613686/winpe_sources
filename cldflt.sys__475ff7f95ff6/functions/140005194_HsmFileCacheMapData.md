# HsmFileCacheMapData

- ea: `0x140005194`
- end: `0x1400054ba`
- name: `HsmFileCacheMapData`
- size: `806`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, union _LARGE_INTEGER, __int64, PVOID *, PVOID *Buffer, ULONG *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140072880`

## callees

- `0x140003c50`
- `0x140005194`
- `0x1400054c0`
- `0x140009300`
- `0x14000dd64`
- `0x14000e99c`
- `0x14001b8dc`
- `0x14001cd3c`
- `0x14001cf88`

## import_xrefs

- `ntoskrnl!CcMapData` at `0x1400052cf`
- `ntoskrnl!CcMapData` at `0x1400052cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005307`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ec10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005307`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ec10`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005289`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005289`

## pseudocode

```c
__int64 __fastcall HsmFileCacheMapData(
        PFILE_OBJECT FileObject,
        union _LARGE_INTEGER a2,
        __int64 a3,
        PVOID *a4,
        PVOID *Buffer,
        ULONG *a6)
{
  __int64 v9; // r14
  signed __int64 v10; // r15
  ULONG v11; // ebx
  int v12; // esi
  PVOID *v13; // r14
  ULONG *v14; // r8
  __int64 v16; // r8
  __int64 v17; // [rsp+30h] [rbp-68h]
  union _LARGE_INTEGER FileOffset; // [rsp+58h] [rbp-40h] BYREF

  v9 = a2.QuadPart + 4096;
  FileOffset.QuadPart = a2.QuadPart + 4096;
  v10 = (a2.QuadPart & 0xFFFFFFFFFFFC0000uLL) + 0x40000;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
  {
    v11 = 4096;
  }
  else
  {
    v11 = 4096;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqd)(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        FileObject,
        (union _LARGE_INTEGER)a2.QuadPart,
        4096);
  }
  *a4 = 0;
  *Buffer = 0;
  *a6 = 0;
  if ( a2.QuadPart < 0 || v9 < 0 || v10 <= a2.QuadPart || v9 <= a2.QuadPart )
  {
    v12 = -1073741595;
    HsmDbgBreakOnStatus(-1073741595);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      HIDWORD(v17) = HIDWORD(v9);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qiDiid)(
        WPP_GLOBAL_Control->AttachedDevice,
        41,
        v16,
        FileObject,
        (union _LARGE_INTEGER)a2.QuadPart);
    }
    goto LABEL_19;
  }
  v12 = HsmiFileCacheValidateFileObject(FileObject, &FileOffset, 0);
  HsmDbgBreakOnStatus(v12);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qDd)(
        WPP_GLOBAL_Control->AttachedDevice,
        42,
        WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
        (union _LARGE_INTEGER)a2.QuadPart,
        4096,
        v12);
    }
LABEL_19:
    v13 = a4;
    v14 = a6;
    goto LABEL_13;
  }
  if ( v10 < v9 )
    v11 = v10 - a2.LowPart;
  KeEnterCriticalRegion();
  FileOffset = a2;
  v13 = a4;
  CcMapData(FileObject, &FileOffset, v11, 1u, a4, Buffer);
  KeLeaveCriticalRegion();
  v14 = a6;
  *a6 = v11;
LABEL_13:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    LODWORD(v17) = v12;
    WPP_SF_qqDd(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
      *v13,
      *Buffer,
      *v14,
      v17);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140005194  mov     rax, rsp
0x140005197  mov     [rax+20h], r9
0x14000519b  mov     [rax+18h], r8d
0x14000519f  mov     [rax+10h], rdx
0x1400051a3  mov     [rax+8], rcx
0x1400051a7  push    rbx
0x1400051a8  push    rsi
0x1400051a9  push    rdi
0x1400051aa  push    r12
0x1400051ac  push    r13
0x1400051ae  push    r14
0x1400051b0  push    r15
0x1400051b2  sub     rsp, 60h
0x1400051b6  mov     rsi, r9
0x1400051b9  mov     rdi, rdx
0x1400051bc  mov     r12, rcx
0x1400051bf  lea     r14, [rdx+1000h]
0x1400051c6  mov     [rax-40h], r14
0x1400051ca  mov     r15, rdx
0x1400051cd  and     r15, 0FFFFFFFFFFFC0000h
0x1400051d4  add     r15, 40000h
0x1400051db  lea     r13, WPP_GLOBAL_Control
0x1400051e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400051e9  cmp     rcx, r13
0x1400051ec  jz      loc_140005384
0x1400051f2  mov     eax, [rcx+2Ch]
0x1400051f5  test    al, 8
0x1400051f7  jz      loc_140005384
0x1400051fd  mov     ebx, 1000h
0x140005202  cmp     byte ptr [rcx+29h], 5
0x140005206  jnb     loc_14000538E
0x14000520c  mov     qword ptr [rsi], 0
0x140005213  mov     rax, [rsp+98h+arg_20]
0x14000521b  mov     qword ptr [rax], 0
0x140005222  mov     rax, [rsp+98h+arg_28]
0x14000522a  mov     dword ptr [rax], 0
0x140005230  test    rdi, rdi
0x140005233  js      loc_140005356
0x140005239  test    r14, r14
0x14000523c  js      loc_140005356
0x140005242  cmp     r15, rdi
0x140005245  jle     loc_140005356
0x14000524b  cmp     r14, rdi
0x14000524e  jle     loc_140005356
0x140005254  xor     r8d, r8d
0x140005257  lea     rdx, [rsp+98h+FileOffset]
0x14000525c  mov     rcx, r12
0x14000525f  call    HsmiFileCacheValidateFileObject
0x140005264  mov     esi, eax
0x140005266  mov     [rsp+98h+var_48], eax
0x14000526a  mov     ecx, eax
0x14000526c  call    HsmDbgBreakOnStatus
0x140005271  test    esi, esi
0x140005273  js      loc_1400053B4
0x140005279  mov     [rsp+98h+arg_10], ebx
0x140005280  cmp     r15, r14
0x140005283  jl      loc_1400053EF
0x140005289  call    cs:__imp_KeEnterCriticalRegion
0x140005290  nop     dword ptr [rax+rax+00h]
0x140005295  nop
0x140005296  mov     qword ptr [rsp+98h+FileOffset], 0
0x14000529f  mov     qword ptr [rsp+98h+FileOffset], rdi
0x1400052a4  mov     rax, [rsp+98h+arg_20]
0x1400052ac  mov     [rsp+98h+Buffer], rax; Buffer
0x1400052b1  mov     r14, [rsp+98h+arg_18]
0x1400052b9  mov     [rsp+98h+Bcb], r14; Bcb
0x1400052be  mov     r9d, 1; Flags
0x1400052c4  mov     r8d, ebx; Length
0x1400052c7  lea     rdx, [rsp+98h+FileOffset]; FileOffset
0x1400052cc  mov     rcx, r12; FileObject
0x1400052cf  call    cs:__imp_CcMapData
0x1400052d6  nop     dword ptr [rax+rax+00h]
0x1400052db  jmp     short loc_140005307
0x1400052dd  lea     r13, WPP_GLOBAL_Control
0x1400052e4  mov     rdi, [rsp+98h+arg_8]
0x1400052ec  mov     r12, [rsp+98h+arg_0]
0x1400052f4  mov     esi, [rsp+98h+var_48]
0x1400052f8  mov     ebx, [rsp+98h+arg_10]
0x1400052ff  mov     r14, [rsp+98h+arg_18]
0x140005307  call    cs:__imp_KeLeaveCriticalRegion
0x14000530e  nop     dword ptr [rax+rax+00h]
0x140005313  test    esi, esi
0x140005315  js      loc_140005400
0x14000531b  mov     r8, [rsp+98h+arg_28]
0x140005323  mov     [r8], ebx
0x140005326  mov     rcx, cs:WPP_GLOBAL_Control
0x14000532d  cmp     rcx, r13
0x140005330  jz      short loc_140005343
0x140005332  mov     eax, [rcx+2Ch]
0x140005335  test    al, 8
0x140005337  jz      short loc_140005343
0x140005339  cmp     byte ptr [rcx+29h], 5
0x14000533d  jnb     loc_140005481
0x140005343  mov     eax, esi
0x140005345  add     rsp, 60h
0x140005349  pop     r15
0x14000534b  pop     r14
0x14000534d  pop     r13
0x14000534f  pop     r12
0x140005351  pop     rdi
0x140005352  pop     rsi
0x140005353  pop     rbx
0x140005354  retn
0x140005356  mov     esi, 0C00000E5h
0x14000535b  mov     ecx, esi
0x14000535d  call    HsmDbgBreakOnStatus
0x140005362  mov     rcx, cs:WPP_GLOBAL_Control
0x140005369  cmp     rcx, r13
0x14000536c  jnz     loc_140005443
0x140005372  mov     r14, [rsp+98h+arg_18]
0x14000537a  mov     r8, [rsp+98h+arg_28]
0x140005382  jmp     short loc_140005326
0x140005384  mov     ebx, 1000h
0x140005389  jmp     loc_14000520C
0x14000538e  mov     edx, 28h ; '('
0x140005393  mov     dword ptr [rsp+98h+Buffer], ebx
0x140005397  mov     [rsp+98h+Bcb], rdi
0x14000539c  mov     r9, r12
0x14000539f  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400053a6  mov     rcx, [rcx+18h]
0x1400053aa  call    WPP_SF_qqd
0x1400053af  jmp     loc_14000520C
0x1400053b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053bb  cmp     rcx, r13
0x1400053be  jz      short loc_140005372
0x1400053c0  mov     eax, [rcx+2Ch]
0x1400053c3  test    al, 8
0x1400053c5  jz      short loc_140005372
0x1400053c7  cmp     byte ptr [rcx+29h], 2
0x1400053cb  jb      short loc_140005372
0x1400053cd  mov     edx, 2Ah ; '*'
0x1400053d2  mov     dword ptr [rsp+98h+Buffer], esi
0x1400053d6  mov     dword ptr [rsp+98h+Bcb], ebx
0x1400053da  mov     r9, rdi
0x1400053dd  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400053e4  mov     rcx, [rcx+18h]
0x1400053e8  call    WPP_SF_qDd
0x1400053ed  jmp     short loc_140005372
0x1400053ef  mov     ebx, r15d
0x1400053f2  sub     ebx, edi
0x1400053f4  mov     [rsp+98h+arg_10], ebx
0x1400053fb  jmp     loc_140005289
0x140005400  mov     rcx, cs:WPP_GLOBAL_Control
0x140005407  cmp     rcx, r13
0x14000540a  jz      loc_14000537A
0x140005410  mov     eax, [rcx+2Ch]
0x140005413  test    al, 8
0x140005415  jz      loc_14000537A
0x14000541b  cmp     byte ptr [rcx+29h], 2
0x14000541f  jb      loc_14000537A
0x140005425  mov     dword ptr [rsp+98h+var_60], esi
0x140005429  mov     dword ptr [rsp+98h+var_68], ebx
0x14000542d  mov     [rsp+98h+Bcb], rdi
0x140005432  mov     r9, r12
0x140005435  mov     rcx, [rcx+18h]
0x140005439  call    WPP_SF_qiDDd
0x14000543e  jmp     loc_14000537A
0x140005443  mov     eax, [rcx+2Ch]
0x140005446  test    al, 8
0x140005448  jz      loc_140005372
0x14000544e  cmp     byte ptr [rcx+29h], 2
0x140005452  jb      loc_140005372
0x140005458  mov     edx, 29h ; ')'
0x14000545d  mov     [rsp+98h+var_58], esi
0x140005461  mov     [rsp+98h+var_60], r15
0x140005466  mov     [rsp+98h+var_68], r14
0x14000546b  mov     [rsp+98h+Bcb], rdi
0x140005470  mov     r9, r12
0x140005473  mov     rcx, [rcx+18h]
0x140005477  call    WPP_SF_qiDiid
0x14000547c  jmp     loc_140005372
0x140005481  mov     edx, 2Ch ; ','
0x140005486  mov     dword ptr [rsp+98h+var_68], esi
0x14000548a  mov     r9d, [r8]
0x14000548d  mov     dword ptr [rsp+98h+Buffer], r9d
0x140005492  mov     rax, [rsp+98h+arg_20]
0x14000549a  mov     r9, [rax]
0x14000549d  mov     [rsp+98h+Bcb], r9
0x1400054a2  mov     r9, [r14]
0x1400054a5  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x1400054ac  mov     rcx, [rcx+18h]
0x1400054b0  call    WPP_SF_qqDd
0x1400054b5  jmp     loc_140005343
0x14001ebed  push    rbp
0x14001ebef  sub     rsp, 50h
0x14001ebf3  mov     rbp, rdx
0x14001ebf6  lea     rdx, [rbp+50h]
0x14001ebfa  call    HsmFileCacheExceptionFilter
0x14001ebff  nop
0x14001ec00  add     rsp, 50h
0x14001ec04  pop     rbp
0x14001ec05  retn
0x14001ec07  push    rbp
0x14001ec09  sub     rsp, 50h
0x14001ec0d  mov     rbp, rdx
0x14001ec10  call    cs:__imp_KeLeaveCriticalRegion
0x14001ec17  nop     dword ptr [rax+rax+00h]
0x14001ec1c  nop
0x14001ec1d  add     rsp, 50h
0x14001ec21  pop     rbp
0x14001ec22  retn
```
