# MessageBoxImpl(HWND__ *,ushort const *,ushort const *,ushort const *,uint)

- ea: `0x18003aad8`
- end: `0x18003b188`
- name: `?MessageBoxImpl@@YAHPEAUHWND__@@PEBG11I@Z`
- size: `1712`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b188`

## callees

- `0x180001e8c`
- `0x18002fb04`
- `0x18002fce8`
- `0x180030d84`
- `0x180032ef4`
- `0x180032f44`
- `0x18003303c`
- `0x18003aad8`
- `0x18003c47c`
- `0x18003dc30`
- `0x18003e73c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18003ad8f`
- `KERNEL32!LoadLibraryExW` at `0x18003ad8f`
- `KERNEL32!FreeLibrary` at `0x18003add6`
- `KERNEL32!FreeLibrary` at `0x18003b151`
- `KERNEL32!FreeLibrary` at `0x18003add6`
- `KERNEL32!FreeLibrary` at `0x18003b151`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003ac30`
- `KERNEL32!GetWindowsDirectoryW` at `0x18003ac30`
- `KERNEL32!ReleaseActCtx` at `0x18003b143`
- `KERNEL32!ReleaseActCtx` at `0x18003b143`
- `KERNEL32!DeactivateActCtx` at `0x18003b13a`
- `KERNEL32!DeactivateActCtx` at `0x18003b13a`
- `KERNEL32!ActivateActCtx` at `0x18003ad6b`
- `KERNEL32!ActivateActCtx` at `0x18003ad6b`
- `KERNEL32!CreateActCtxW` at `0x18003ad54`
- `KERNEL32!CreateActCtxW` at `0x18003ad54`
- `KERNEL32!GetProcAddress` at `0x18003adbc`
- `KERNEL32!GetProcAddress` at `0x18003adbc`
- `KERNEL32!HeapFree` at `0x18003ae2b`
- `KERNEL32!HeapFree` at `0x18003b093`
- `KERNEL32!HeapFree` at `0x18003b0d0`
- `KERNEL32!HeapFree` at `0x18003b10d`
- `KERNEL32!HeapFree` at `0x18003ae2b`
- `KERNEL32!HeapFree` at `0x18003b093`
- `KERNEL32!HeapFree` at `0x18003b0d0`
- `KERNEL32!HeapFree` at `0x18003b10d`
- `KERNEL32!GetProcessHeap` at `0x18003ae16`
- `KERNEL32!GetProcessHeap` at `0x18003b07e`
- `KERNEL32!GetProcessHeap` at `0x18003b0bb`
- `KERNEL32!GetProcessHeap` at `0x18003b0f8`
- `KERNEL32!GetProcessHeap` at `0x18003ae16`
- `KERNEL32!GetProcessHeap` at `0x18003b07e`
- `KERNEL32!GetProcessHeap` at `0x18003b0bb`
- `KERNEL32!GetProcessHeap` at `0x18003b0f8`

## string_xrefs

- `0x18003ad2e`: `WindowsShell.manifest`
- `0x18003ad88`: `comctl32.dll`
- `0x18003adb2`: `TaskDialogIndirect`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall MessageBoxImpl(
        HWND a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  HWND v5; // rcx
  FARPROC ProcAddress; // r12
  HMODULE Library; // r14
  int v8; // ebx
  __int64 v9; // r13
  unsigned int v10; // esi
  char v11; // dl
  unsigned int v12; // edi
  unsigned int v13; // eax
  UINT WindowsDirectoryW; // edx
  unsigned int v15; // r10d
  char *v16; // rcx
  unsigned int v17; // edx
  int v18; // edi
  int v19; // edx
  __int16 v20; // cx
  HANDLE v21; // rax
  bool v22; // r12
  LPWSTR v23; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v25; // rdx
  const wchar_t *v26; // r15
  __int64 v27; // rdx
  const wchar_t *v28; // rdi
  const wchar_t *v29; // rax
  void *v30; // rdi
  HANDLE v31; // rax
  void *v32; // rdi
  HANDLE v33; // rax
  void *v34; // rdi
  HANDLE v35; // rax
  char v37; // [rsp+30h] [rbp-D0h]
  unsigned int v38; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v39; // [rsp+38h] [rbp-C8h]
  ULONG_PTR Cookie; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int (__fastcall *v41)(int *, unsigned int *, _QWORD, _QWORD); // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v42; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v43; // [rsp+58h] [rbp-A8h]
  HMODULE v44; // [rsp+60h] [rbp-A0h]
  int v45; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v46; // [rsp+70h] [rbp-90h]
  ACTCTXW pActCtx; // [rsp+78h] [rbp-88h] BYREF
  int v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B4h] [rbp-4Ch]
  unsigned int v50; // [rsp+C4h] [rbp-3Ch]
  int v51; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v52; // [rsp+CCh] [rbp-34h]
  __int64 v53; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 *v54; // [rsp+DCh] [rbp-24h]
  unsigned __int16 *v55; // [rsp+E4h] [rbp-1Ch]
  int v56; // [rsp+ECh] [rbp-14h]
  int *v57; // [rsp+F0h] [rbp-10h]
  const unsigned __int16 *v58; // [rsp+114h] [rbp+14h]
  unsigned int v59; // [rsp+150h] [rbp+50h] BYREF
  __int64 v60; // [rsp+154h] [rbp+54h]
  LPWSTR lpBuffer; // [rsp+160h] [rbp+60h]
  __int16 v62; // [rsp+168h] [rbp+68h] BYREF
  int v63; // [rsp+370h] [rbp+270h] BYREF
  __int64 v64; // [rsp+374h] [rbp+274h]
  LPVOID lpMem; // [rsp+380h] [rbp+280h]
  __int16 v66; // [rsp+388h] [rbp+288h] BYREF
  int v67; // [rsp+590h] [rbp+490h] BYREF
  __int64 v68; // [rsp+594h] [rbp+494h]
  LPVOID v69; // [rsp+5A0h] [rbp+4A0h]
  __int16 v70; // [rsp+5A8h] [rbp+4A8h] BYREF
  int v71; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int64 v72; // [rsp+7B4h] [rbp+6B4h]
  LPVOID v73; // [rsp+7C0h] [rbp+6C0h]
  __int16 v74; // [rsp+7C8h] [rbp+6C8h] BYREF
  int v75; // [rsp+9D0h] [rbp+8D0h] BYREF
  const wchar_t *v76; // [rsp+9D4h] [rbp+8D4h]
  int v77; // [rsp+9DCh] [rbp+8DCh]
  const wchar_t *v78; // [rsp+9E0h] [rbp+8E0h]
  int v79; // [rsp+9E8h] [rbp+8E8h]
  const wchar_t *v80; // [rsp+9ECh] [rbp+8ECh]

  v46 = a4;
  v42 = a3;
  v43 = a2;
  v5 = 0;
  ProcAddress = 0;
  v41 = 0;
  Cookie = 0;
  v37 = 0;
  Library = 0;
  v44 = 0;
  v8 = 0;
  v45 = 0;
  v9 = -1;
  v39 = a5 & 0xF0;
  if ( ((v39 - 16) & 0xFFFFFFDF) != 0 )
    goto LABEL_71;
  v10 = 2;
  if ( (a5 & 0xF) != 2 || (a5 & 0xFF00) != 0 || dword_180070690 == 1 )
    goto LABEL_71;
  pActCtx.cbSize = 56;
  memset(&pActCtx.dwFlags, 0, 52);
  pActCtx.dwFlags = 0;
  v60 = 512;
  lpBuffer = (LPWSTR)&v62;
  v59 = 2;
  v62 = 0;
  SString::Resize(&v59, 260, 4);
  v11 = BYTE4(v60);
  v12 = 261 << ((v60 & 0x100000000LL) == 0);
  v13 = v60;
  if ( v12 > (unsigned int)v60 )
  {
    SBuffer::ReallocateBuffer(&v59, v12, 1);
    v11 = BYTE4(v60);
    v13 = v60;
  }
  v59 = v12;
  if ( (v11 & 0x10) != 0 )
    SBuffer::ReallocateBuffer(&v59, v13, 1);
  WindowsDirectoryW = GetWindowsDirectoryW(lpBuffer, 0x104u);
  if ( WindowsDirectoryW - 1 <= 0x102 )
  {
    v15 = 1;
    v59 = (WindowsDirectoryW + 1) << ((v60 & 0x100000000LL) == 0);
    v16 = (char *)lpBuffer + v59;
    if ( (v60 & 0x100000000LL) != 0 )
      *(v16 - 1) = 0;
    else
      *((_WORD *)v16 - 1) = 0;
    v17 = HIDWORD(v60);
    if ( (v60 & 0x200000000LL) != 0 && ((BYTE4(v60) & 7) != 7 || SString::s_IsANSIMultibyte) )
    {
      if ( !(unsigned int)SString::ScanASCII((SString *)&v59) )
      {
        SString::ConvertToUnicode((SString *)&v59);
        v15 = 1;
      }
      v17 = HIDWORD(v60);
    }
    v18 = (v59 >> (v15 & ~(_BYTE)v17)) - 2;
    if ( ((unsigned __int8)~(v17 >> 1) & (unsigned __int8)v15) == 0 )
    {
      if ( !(unsigned int)SString::ScanASCII((SString *)&v59) )
      {
        SString::ConvertToUnicode((SString *)&v59);
        v15 = 1;
      }
      LOBYTE(v17) = BYTE4(v60);
    }
    if ( (v17 & 0x10) != 0 )
    {
      SBuffer::ReallocateBuffer(&v59, (unsigned int)v60, v15);
      LOBYTE(v17) = BYTE4(v60);
    }
    v19 = (v17 & 1) == 0;
    if ( v19 )
      v20 = *(LPWSTR)((char *)lpBuffer + (v18 << v19));
    else
      v20 = *((char *)lpBuffer + v18);
    if ( v20 != 92 )
      SString::Append((SString *)&v59, v19);
    SString::Append((SString *)&v59, L"WindowsShell.manifest");
    SString::ConvertToUnicode((SString *)&v59);
    pActCtx.lpSource = lpBuffer;
    v21 = CreateActCtxW(&pActCtx);
    v9 = (__int64)v21;
    if ( v21 != (HANDLE)-1LL )
    {
      if ( ActivateActCtx(v21, &Cookie) )
      {
        v37 = 1;
        Library = LoadLibraryExW(L"comctl32.dll", 0, 0);
        v44 = Library;
        if ( Library )
          v8 = 1;
        v45 = v8;
        if ( Library != (HMODULE)-1LL )
        {
          ProcAddress = GetProcAddress(Library, "TaskDialogIndirect");
          v41 = (unsigned int (__fastcall *)(int *, unsigned int *, _QWORD, _QWORD))ProcAddress;
          if ( !ProcAddress )
          {
            if ( v8 )
            {
              FreeLibrary(Library);
              v8 = 0;
              v45 = 0;
            }
          }
        }
      }
      else
      {
        Cookie = 0;
      }
    }
  }
  v5 = (HWND)-(__int64)ProcAddress;
  dword_180070690 = (ProcAddress != 0) + 1;
  v22 = ProcAddress == 0;
  if ( (v60 & 0x800000000LL) != 0 )
  {
    v23 = lpBuffer;
    if ( lpBuffer )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v23);
    }
  }
  if ( v22 )
  {
LABEL_71:
    v10 = LateboundMessageBoxW(v5, v43, v42, a5);
  }
  else
  {
    v38 = 0;
    memset_0(&v48, 0, 0xA0u);
    v48 = 160;
    v49 = 0;
    v51 = 0;
    v52 = v42;
    v50 = (a5 >> 7) & 0x2000;
    v53 = 0xFFFFLL - (v39 != 48);
    v54 = v42;
    v55 = v43;
    v58 = v46;
    v72 = 512;
    v73 = &v74;
    v71 = 2;
    v74 = 0;
    v68 = 512;
    v69 = &v70;
    v67 = 2;
    v70 = 0;
    v64 = 512;
    lpMem = &v66;
    v63 = 2;
    v66 = 0;
    if ( (int)SString::LoadResourceAndReturnHR(&v71, v43, 4, 9730) < 0 )
    {
      v26 = L"&Abort";
    }
    else
    {
      SString::ConvertToUnicode((SString *)&v71);
      v26 = (const wchar_t *)v73;
    }
    if ( (int)SString::LoadResourceAndReturnHR(&v67, v25, 4, 9731) < 0 )
    {
      v28 = L"&Debug";
    }
    else
    {
      SString::ConvertToUnicode((SString *)&v67);
      v28 = (const wchar_t *)v69;
    }
    if ( (int)SString::LoadResourceAndReturnHR(&v63, v27, 4, 9732) < 0 )
    {
      v29 = L"&Ignore";
    }
    else
    {
      SString::ConvertToUnicode((SString *)&v63);
      v29 = (const wchar_t *)lpMem;
    }
    v75 = 1;
    v76 = v26;
    v77 = 4;
    v78 = v28;
    v79 = 5;
    v80 = v29;
    v57 = &v75;
    v56 = 3;
    if ( !v41(&v48, &v38, 0, 0) )
      v10 = v38;
    if ( (v64 & 0x800000000LL) != 0 )
    {
      v30 = lpMem;
      if ( lpMem )
      {
        v31 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v31 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v31;
        }
        HeapFree(v31, 0, v30);
      }
    }
    if ( (v68 & 0x800000000LL) != 0 )
    {
      v32 = v69;
      if ( v69 )
      {
        v33 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v33 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v33;
        }
        HeapFree(v33, 0, v32);
      }
    }
    if ( (v72 & 0x800000000LL) != 0 )
    {
      v34 = v73;
      if ( v73 )
      {
        v35 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v35 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v35;
        }
        HeapFree(v35, 0, v34);
      }
    }
  }
  if ( v37 )
  {
    DeactivateActCtx(0, Cookie);
    ReleaseActCtx((HANDLE)v9);
  }
  if ( v8 )
  {
    FreeLibrary(Library);
    v45 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18003aad8  mov     [rsp-8+arg_0], rbx
0x18003aadd  push    rbp
0x18003aade  push    rsi
0x18003aadf  push    rdi
0x18003aae0  push    r12
0x18003aae2  push    r13
0x18003aae4  push    r14
0x18003aae6  push    r15
0x18003aae8  lea     rbp, [rsp-900h]
0x18003aaf0  sub     rsp, 0A00h
0x18003aaf7  mov     rax, cs:__security_cookie
0x18003aafe  xor     rax, rsp
0x18003ab01  mov     [rbp+930h+var_38], rax
0x18003ab08  mov     [rsp+0A30h+var_9C0], r9
0x18003ab0d  mov     [rsp+0A30h+var_9E0], r8
0x18003ab12  mov     [rsp+0A30h+var_9D8], rdx
0x18003ab17  mov     r15d, [rbp+930h+arg_20]
0x18003ab1e  xor     ecx, ecx; HWND
0x18003ab20  mov     r12d, ecx
0x18003ab23  mov     [rsp+0A30h+var_9E8], rcx
0x18003ab28  mov     [rsp+0A30h+Cookie], rcx
0x18003ab2d  mov     [rsp+0A30h+var_A00], cl
0x18003ab31  mov     r14d, ecx
0x18003ab34  mov     [rsp+0A30h+var_9D0], rcx
0x18003ab39  mov     ebx, ecx
0x18003ab3b  mov     [rsp+0A30h+var_9C8], ecx
0x18003ab3f  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003ab43  mov     eax, r15d
0x18003ab46  and     eax, 0F0h
0x18003ab4b  mov     [rsp+0A30h+var_9F8], eax
0x18003ab4f  add     eax, 0FFFFFFF0h
0x18003ab52  test    eax, 0FFFFFFDFh
0x18003ab57  jnz     loc_18003B115
0x18003ab5d  mov     eax, r15d
0x18003ab60  and     al, 0Fh
0x18003ab62  lea     esi, [rcx+2]
0x18003ab65  cmp     al, sil
0x18003ab68  jnz     loc_18003B115
0x18003ab6e  test    r15d, 0FF00h
0x18003ab75  jnz     loc_18003B115
0x18003ab7b  lea     edi, [rcx+1]
0x18003ab7e  cmp     cs:dword_180070690, edi
0x18003ab84  jz      loc_18003B115
0x18003ab8a  mov     [rsp+0A30h+pActCtx.cbSize], 38h ; '8'
0x18003ab92  xorps   xmm0, xmm0
0x18003ab95  xor     eax, eax
0x18003ab97  movups  xmmword ptr [rsp+0A30h+pActCtx.dwFlags], xmm0
0x18003ab9c  movups  xmmword ptr [rbp+930h+pActCtx+14h], xmm0
0x18003aba0  movups  xmmword ptr [rbp+930h+pActCtx.lpResourceName+4], xmm0
0x18003aba4  mov     dword ptr [rbp+930h+pActCtx.hModule+4], eax
0x18003aba7  mov     [rsp+0A30h+pActCtx.dwFlags], ecx
0x18003abab  mov     [rbp+930h+var_8E0], rcx
0x18003abaf  mov     [rbp+930h+var_8E0+4], 200h
0x18003abb7  mov     [rbp+930h+lpBuffer], rcx
0x18003abbb  lea     rax, [rbp+930h+var_8C8]
0x18003abbf  mov     [rbp+930h+lpBuffer], rax
0x18003abc3  mov     dword ptr [rbp+930h+var_8E0], esi
0x18003abc6  mov     rax, [rbp+930h+lpBuffer]
0x18003abca  mov     [rax], cx
0x18003abcd  xor     r9d, r9d
0x18003abd0  mov     edx, 104h
0x18003abd5  lea     r8d, [rcx+4]
0x18003abd9  lea     rcx, [rbp+930h+var_8E0]
0x18003abdd  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x18003abe2  mov     edx, [rbp+930h+var_8D8]
0x18003abe5  mov     ecx, edx
0x18003abe7  not     ecx
0x18003abe9  and     ecx, edi
0x18003abeb  mov     edi, 105h
0x18003abf0  shl     edi, cl
0x18003abf2  mov     eax, dword ptr [rbp+930h+var_8E0+4]
0x18003abf5  cmp     edi, eax
0x18003abf7  jbe     short loc_18003AC0E
0x18003abf9  lea     r8d, [r14+1]
0x18003abfd  mov     edx, edi
0x18003abff  lea     rcx, [rbp+930h+var_8E0]
0x18003ac03  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003ac08  mov     edx, [rbp+930h+var_8D8]
0x18003ac0b  mov     eax, dword ptr [rbp+930h+var_8E0+4]
0x18003ac0e  mov     dword ptr [rbp+930h+var_8E0], edi
0x18003ac11  test    dl, 10h
0x18003ac14  jz      short loc_18003AC27
0x18003ac16  mov     r8d, 1
0x18003ac1c  mov     edx, eax
0x18003ac1e  lea     rcx, [rbp+930h+var_8E0]
0x18003ac22  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003ac27  mov     edx, 104h; uSize
0x18003ac2c  mov     rcx, [rbp+930h+lpBuffer]; lpBuffer
0x18003ac30  call    cs:__imp_GetWindowsDirectoryW
0x18003ac36  mov     edx, eax
0x18003ac38  dec     eax
0x18003ac3a  cmp     eax, 102h
0x18003ac3f  ja      loc_18003ADE2
0x18003ac45  mov     ecx, [rbp+930h+var_8D8]
0x18003ac48  not     ecx
0x18003ac4a  mov     r10d, 1
0x18003ac50  and     ecx, r10d
0x18003ac53  lea     eax, [rdx+1]
0x18003ac56  shl     eax, cl
0x18003ac58  mov     ecx, eax
0x18003ac5a  mov     dword ptr [rbp+930h+var_8E0], ecx
0x18003ac5d  add     rcx, [rbp+930h+lpBuffer]
0x18003ac61  xor     r13d, r13d
0x18003ac64  test    byte ptr [rbp+930h+var_8D8], r10b
0x18003ac68  jz      short loc_18003AC70
0x18003ac6a  mov     [rcx-1], r13b
0x18003ac6e  jmp     short loc_18003AC75
0x18003ac70  mov     [rcx-2], r13w
0x18003ac75  mov     edx, [rbp+930h+var_8D8]
0x18003ac78  test    sil, dl
0x18003ac7b  jz      short loc_18003ACAE
0x18003ac7d  mov     eax, edx
0x18003ac7f  and     eax, 7
0x18003ac82  cmp     al, 7
0x18003ac84  jnz     short loc_18003AC8F
0x18003ac86  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r13d; int SString::s_IsANSIMultibyte
0x18003ac8d  jz      short loc_18003ACAE
0x18003ac8f  lea     rcx, [rbp+930h+var_8E0]; this
0x18003ac93  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003ac98  test    eax, eax
0x18003ac9a  jnz     short loc_18003ACAB
0x18003ac9c  lea     rcx, [rbp+930h+var_8E0]; this
0x18003aca0  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003aca5  mov     r10d, 1
0x18003acab  mov     edx, [rbp+930h+var_8D8]
0x18003acae  mov     ecx, edx
0x18003acb0  not     ecx
0x18003acb2  and     ecx, r10d
0x18003acb5  mov     edi, dword ptr [rbp+930h+var_8E0]
0x18003acb8  shr     edi, cl
0x18003acba  add     edi, 0FFFFFFFEh
0x18003acbd  mov     eax, edx
0x18003acbf  shr     eax, 1
0x18003acc1  not     eax
0x18003acc3  test    r10b, al
0x18003acc6  jnz     short loc_18003ACE7
0x18003acc8  lea     rcx, [rbp+930h+var_8E0]; this
0x18003accc  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18003acd1  test    eax, eax
0x18003acd3  jnz     short loc_18003ACE4
0x18003acd5  lea     rcx, [rbp+930h+var_8E0]; this
0x18003acd9  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003acde  mov     r10d, 1
0x18003ace4  mov     edx, [rbp+930h+var_8D8]
0x18003ace7  test    dl, 10h
0x18003acea  jz      short loc_18003ACFE
0x18003acec  mov     r8d, r10d
0x18003acef  mov     edx, dword ptr [rbp+930h+var_8E0+4]
0x18003acf2  lea     rcx, [rbp+930h+var_8E0]
0x18003acf6  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18003acfb  mov     edx, [rbp+930h+var_8D8]
0x18003acfe  mov     r8, [rbp+930h+lpBuffer]
0x18003ad02  not     edx
0x18003ad04  and     edx, 1; unsigned __int16
0x18003ad07  jnz     short loc_18003AD13
0x18003ad09  movsxd  rax, edi
0x18003ad0c  movsx   ecx, byte ptr [rax+r8]
0x18003ad11  jmp     short loc_18003AD1F
0x18003ad13  mov     ecx, edx
0x18003ad15  shl     edi, cl
0x18003ad17  movsxd  rax, edi
0x18003ad1a  movzx   ecx, word ptr [rax+r8]
0x18003ad1f  cmp     cx, 5Ch ; '\'
0x18003ad23  jz      short loc_18003AD2E
0x18003ad25  lea     rcx, [rbp+930h+var_8E0]; this
0x18003ad29  call    ?Append@SString@@QEAAXG@Z; SString::Append(ushort)
0x18003ad2e  lea     rdx, aWindowsshellMa; "WindowsShell.manifest"
0x18003ad35  lea     rcx, [rbp+930h+var_8E0]; this
0x18003ad39  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18003ad3e  lea     rcx, [rbp+930h+var_8E0]; this
0x18003ad42  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003ad47  mov     rax, [rbp+930h+lpBuffer]
0x18003ad4b  mov     [rbp+930h+pActCtx.lpSource], rax
0x18003ad4f  lea     rcx, [rsp+0A30h+pActCtx]; pActCtx
0x18003ad54  call    cs:__imp_CreateActCtxW
0x18003ad5a  mov     r13, rax
0x18003ad5d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003ad61  jz      short loc_18003ADE2
0x18003ad63  lea     rdx, [rsp+0A30h+Cookie]; lpCookie
0x18003ad68  mov     rcx, rax; hActCtx
0x18003ad6b  call    cs:__imp_ActivateActCtx
0x18003ad71  xor     edi, edi
0x18003ad73  test    eax, eax
0x18003ad75  jnz     short loc_18003AD7E
0x18003ad77  mov     [rsp+0A30h+Cookie], rdi
0x18003ad7c  jmp     short loc_18003ADE2
0x18003ad7e  mov     [rsp+0A30h+var_A00], 1
0x18003ad83  xor     r8d, r8d; dwFlags
0x18003ad86  xor     edx, edx; hFile
0x18003ad88  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18003ad8f  call    cs:__imp_LoadLibraryExW
0x18003ad95  mov     r14, rax
0x18003ad98  mov     [rsp+0A30h+var_9D0], rax
0x18003ad9d  test    rax, rax
0x18003ada0  mov     eax, 1
0x18003ada5  cmovnz  ebx, eax
0x18003ada8  mov     [rsp+0A30h+var_9C8], ebx
0x18003adac  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18003adb0  jz      short loc_18003ADE2
0x18003adb2  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x18003adb9  mov     rcx, r14; hModule
0x18003adbc  call    cs:__imp_GetProcAddress
0x18003adc2  mov     r12, rax
0x18003adc5  mov     [rsp+0A30h+var_9E8], rax
0x18003adca  test    rax, rax
0x18003adcd  jnz     short loc_18003ADE2
0x18003adcf  test    ebx, ebx
0x18003add1  jz      short loc_18003ADE2
0x18003add3  mov     rcx, r14; hLibModule
0x18003add6  call    cs:__imp_FreeLibrary
0x18003addc  mov     ebx, edi
0x18003adde  mov     [rsp+0A30h+var_9C8], ebx
0x18003ade2  mov     rcx, r12
0x18003ade5  neg     rcx
0x18003ade8  sbb     eax, eax
0x18003adea  neg     eax
0x18003adec  inc     eax
0x18003adee  mov     cs:dword_180070690, eax
0x18003adf4  test    r12, r12
0x18003adf7  setz    r12b
0x18003adfb  test    byte ptr [rbp+930h+var_8D8], 8
0x18003adff  jz      short loc_18003AE31
0x18003ae01  mov     rdi, [rbp+930h+lpBuffer]
0x18003ae05  test    rdi, rdi
0x18003ae08  jz      short loc_18003AE31
0x18003ae0a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003ae11  test    rax, rax
0x18003ae14  jnz     short loc_18003AE23
0x18003ae16  call    cs:__imp_GetProcessHeap
0x18003ae1c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003ae23  mov     r8, rdi; lpMem
0x18003ae26  xor     edx, edx; dwFlags
0x18003ae28  mov     rcx, rax; hHeap
0x18003ae2b  call    cs:__imp_HeapFree
0x18003ae31  test    r12b, r12b
0x18003ae34  jnz     loc_18003B115
0x18003ae3a  xor     r12d, r12d
0x18003ae3d  mov     [rsp+0A30h+var_9FC], r12d
0x18003ae42  mov     edi, 0A0h
0x18003ae47  mov     r8d, edi; Size
0x18003ae4a  xor     edx, edx; Val
0x18003ae4c  lea     rcx, [rbp+930h+var_980]; void *
0x18003ae50  call    memset_0
0x18003ae55  mov     [rbp+930h+var_980], edi
0x18003ae58  mov     [rbp+930h+var_97C], r12
0x18003ae5c  mov     [rbp+930h+var_968], r12d
0x18003ae60  mov     r8, [rsp+0A30h+var_9E0]
0x18003ae65  mov     [rbp+930h+var_964], r8
0x18003ae69  shr     r15d, 7
0x18003ae6d  and     r15d, 2000h
0x18003ae74  mov     [rbp+930h+var_96C], r15d
0x18003ae78  mov     eax, [rsp+0A30h+var_9F8]
0x18003ae7c  sub     eax, 30h ; '0'
0x18003ae7f  neg     eax
0x18003ae81  sbb     rax, rax
0x18003ae84  add     rax, 0FFFFh
0x18003ae8a  mov     [rbp+930h+var_95C], rax
0x18003ae8e  mov     [rbp+930h+var_954], r8
0x18003ae92  mov     rdx, [rsp+0A30h+var_9D8]
0x18003ae97  mov     [rbp+930h+var_94C], rdx
0x18003ae9b  mov     rax, [rsp+0A30h+var_9C0]
0x18003aea0  mov     [rbp+930h+var_91C], rax
0x18003aea4  mov     [rbp+930h+var_280], r12
0x18003aeab  mov     [rbp+930h+var_280+4], 200h
0x18003aeb6  mov     [rbp+930h+var_270], r12
0x18003aebd  lea     rax, [rbp+930h+var_268]
0x18003aec4  mov     [rbp+930h+var_270], rax
0x18003aecb  mov     dword ptr [rbp+930h+var_280], esi
0x18003aed1  mov     rax, [rbp+930h+var_270]
0x18003aed8  mov     [rax], r12w
0x18003aedc  mov     [rbp+930h+var_4A0], r12
0x18003aee3  mov     [rbp+930h+var_4A0+4], 200h
0x18003aeee  mov     [rbp+930h+var_490], r12
0x18003aef5  lea     rax, [rbp+930h+var_488]
0x18003aefc  mov     [rbp+930h+var_490], rax
0x18003af03  mov     dword ptr [rbp+930h+var_4A0], esi
0x18003af09  mov     rax, [rbp+930h+var_490]
0x18003af10  mov     [rax], r12w
0x18003af14  mov     [rbp+930h+var_6C0], r12
0x18003af1b  mov     [rbp+930h+var_6C0+4], 200h
0x18003af26  mov     [rbp+930h+lpMem], r12
0x18003af2d  lea     rax, [rbp+930h+var_6A8]
0x18003af34  mov     [rbp+930h+lpMem], rax
0x18003af3b  mov     dword ptr [rbp+930h+var_6C0], esi
0x18003af41  mov     rax, [rbp+930h+lpMem]
0x18003af48  mov     [rax], r12w
0x18003af4c  lea     edi, [r12+4]
0x18003af51  mov     r9d, 2602h
0x18003af57  mov     r8d, edi
0x18003af5a  lea     rcx, [rbp+930h+var_280]
0x18003af61  call    ?LoadResourceAndReturnHR@SString@@QEAAJPEAVCCompRC@@W4ResourceCategory@2@H@Z; SString::LoadResourceAndReturnHR(CCompRC *,CCompRC::ResourceCategory,int)
0x18003af66  test    eax, eax
0x18003af68  js      short loc_18003AF7F
0x18003af6a  lea     rcx, [rbp+930h+var_280]; this
0x18003af71  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18003af76  mov     r15, [rbp+930h+var_270]
0x18003af7d  jmp     short loc_18003AF86
0x18003af7f  lea     r15, aAbort; "&Abort"
0x18003af86  mov     r9d, 2603h
0x18003af8c  mov     r8d, edi
  ... truncated ...
```
