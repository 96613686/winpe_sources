# CReplCover::Initialize(void)

- ea: `0x10027860`
- end: `0x1002798b`
- name: `?Initialize@CReplCover@@QAEJXZ`
- size: `299`
- prototype: `int __thiscall(CReplCover *__hidden this)`
- caller_count: `14`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x10025bf0`
- `0x10025e70`
- `0x10026240`
- `0x10026380`
- `0x10026470`
- `0x100265e0`
- `0x10026740`
- `0x10026890`
- `0x10027410`
- `0x10027660`
- `0x100279a0`
- `0x100279f0`
- `0x1003e7d0`
- `0x1003e990`

## callees

- `0x1000ba90`
- `0x10027860`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1002794a`
- `KERNEL32!FreeLibrary` at `0x1002794a`
- `KERNEL32!GetProcAddress` at `0x1002790c`
- `KERNEL32!GetProcAddress` at `0x1002790c`
- `KERNEL32!LoadLibraryExA` at `0x100278ce`
- `KERNEL32!LoadLibraryExA` at `0x100278ce`
- `KERNEL32!LeaveCriticalSection` at `0x10027970`
- `KERNEL32!LeaveCriticalSection` at `0x10027970`
- `KERNEL32!EnterCriticalSection` at `0x100278a7`
- `KERNEL32!EnterCriticalSection` at `0x100278a7`

## string_xrefs

- `0x100278c9`: `MSREPL40.DLL`

## pseudocode

```c
int __thiscall CReplCover::Initialize(CReplCover *this)
{
  CReplCover *v1; // edi
  struct _RTL_CRITICAL_SECTION *v2; // esi
  HMODULE Library; // eax
  void **v4; // ebx
  void *v5; // eax
  int v6; // edi
  int v9; // [esp+18h] [ebp-10h]

  v1 = this;
  v2 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 1) + 100);
  v9 = 0;
  EnterCriticalSection(v2);
  if ( *(_DWORD *)(*((_DWORD *)v1 + 1) + 136) == 1 )
  {
    v9 = 0;
    goto LABEL_17;
  }
  Library = LoadLibraryExA("MSREPL40.DLL", 0, 8u);
  *(_DWORD *)v1 = Library;
  v4 = (void **)((char *)v1 + 8);
  if ( Library )
  {
    v5 = operator new(0x30u);
    *v4 = v5;
    if ( !v5 )
    {
      v9 = -2147024882;
      goto LABEL_12;
    }
    v6 = 0;
    while ( 1 )
    {
      *((_DWORD *)*v4 + v6) = GetProcAddress(*(HMODULE *)this, (&lpProcName)[v6]);
      if ( !*((_DWORD *)*v4 + v6) )
        break;
      if ( ++v6 >= 12 )
      {
        *(_DWORD *)(*((_DWORD *)this + 1) + 136) = 1;
        goto LABEL_17;
      }
    }
    v1 = this;
  }
  v9 = -2147467259;
LABEL_12:
  if ( *(_DWORD *)v1 && FreeLibrary(*(HMODULE *)v1) )
    *(_DWORD *)v1 = 0;
  if ( *v4 )
  {
    operator delete(*v4);
    *v4 = 0;
  }
LABEL_17:
  LeaveCriticalSection(v2);
  return v9;
}

```

## disassembly

```asm
0x10027860  mov     edi, edi
0x10027862  push    ebp
0x10027863  mov     ebp, esp
0x10027865  push    0FFFFFFFFh
0x10027867  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x1002786c  mov     eax, large fs:0
0x10027872  push    eax
0x10027873  sub     esp, 0Ch
0x10027876  push    ebx
0x10027877  push    esi
0x10027878  push    edi
0x10027879  mov     eax, ___security_cookie
0x1002787e  xor     eax, ebp
0x10027880  push    eax
0x10027881  lea     eax, [ebp+var_C]
0x10027884  mov     large fs:0, eax
0x1002788a  mov     edi, ecx
0x1002788c  mov     [ebp+var_14], edi
0x1002788f  mov     [ebp+var_4], 0
0x10027896  mov     esi, [edi+4]
0x10027899  add     esi, 64h ; 'd'
0x1002789c  mov     [ebp+var_10], 0
0x100278a3  push    esi; lpCriticalSection
0x100278a4  mov     [ebp+var_18], esi
0x100278a7  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100278ad  mov     eax, [edi+4]
0x100278b0  cmp     dword ptr [eax+88h], 1
0x100278b7  jnz     short loc_100278C5
0x100278b9  mov     [ebp+var_10], 0
0x100278c0  jmp     loc_1002796F
0x100278c5  push    8; dwFlags
0x100278c7  push    0; hFile
0x100278c9  push    offset LibFileName; "MSREPL40.DLL"
0x100278ce  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x100278d4  mov     [edi], eax
0x100278d6  lea     ebx, [edi+8]
0x100278d9  test    eax, eax
0x100278db  jz      short loc_1002793C
0x100278dd  push    30h ; '0'; Size
0x100278df  call    ??2@YAPAXI@Z; operator new(uint)
0x100278e4  add     esp, 4
0x100278e7  mov     [ebx], eax
0x100278e9  test    eax, eax
0x100278eb  jnz     short loc_100278F6
0x100278ed  mov     [ebp+var_10], 8007000Eh
0x100278f4  jmp     short loc_10027943
0x100278f6  xor     edi, edi
0x100278f8  nop     dword ptr [eax+eax+00000000h]
0x10027900  mov     eax, [ebp+var_14]
0x10027903  push    ds:lpProcName[edi*4]; lpProcName
0x1002790a  push    dword ptr [eax]; hModule
0x1002790c  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10027912  mov     ecx, eax
0x10027914  mov     eax, [ebx]
0x10027916  mov     [eax+edi*4], ecx
0x10027919  mov     eax, [ebx]
0x1002791b  cmp     dword ptr [eax+edi*4], 0
0x1002791f  jz      short loc_10027939
0x10027921  inc     edi
0x10027922  cmp     edi, 0Ch
0x10027925  jl      short loc_10027900
0x10027927  mov     eax, [ebp+var_14]
0x1002792a  mov     eax, [eax+4]
0x1002792d  mov     dword ptr [eax+88h], 1
0x10027937  jmp     short loc_1002796F
0x10027939  mov     edi, [ebp+var_14]
0x1002793c  mov     [ebp+var_10], 80004005h
0x10027943  mov     eax, [edi]
0x10027945  test    eax, eax
0x10027947  jz      short loc_1002795A
0x10027949  push    eax; hLibModule
0x1002794a  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10027950  test    eax, eax
0x10027952  jz      short loc_1002795A
0x10027954  mov     dword ptr [edi], 0
0x1002795a  mov     eax, [ebx]
0x1002795c  test    eax, eax
0x1002795e  jz      short loc_1002796F
0x10027960  push    eax; Block
0x10027961  call    ??3@YAXPAX@Z; operator delete(void *)
0x10027966  add     esp, 4
0x10027969  mov     dword ptr [ebx], 0
0x1002796f  push    esi; lpCriticalSection
0x10027970  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10027976  mov     eax, [ebp+var_10]
0x10027979  mov     ecx, [ebp+var_C]
0x1002797c  mov     large fs:0, ecx
0x10027983  pop     ecx
0x10027984  pop     edi
0x10027985  pop     esi
0x10027986  pop     ebx
0x10027987  mov     esp, ebp
0x10027989  pop     ebp
0x1002798a  retn
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
