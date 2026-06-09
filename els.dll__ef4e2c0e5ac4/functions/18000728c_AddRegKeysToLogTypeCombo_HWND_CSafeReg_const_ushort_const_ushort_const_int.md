# _AddRegKeysToLogTypeCombo(HWND__ *,CSafeReg const &,ushort const *,ushort const *,int)

- ea: `0x18000728c`
- end: `0x18000741b`
- name: `?_AddRegKeysToLogTypeCombo@@YAXPEAUHWND__@@AEBVCSafeReg@@PEBG2H@Z`
- size: `399`
- prototype: `void __fastcall(HWND hWnd, const struct CSafeReg *this, wchar_t *Source, const unsigned __int16 *Src, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000839c`

## callees

- `0x180001750`
- `0x180002928`
- `0x18000728c`
- `0x18001adf4`
- `0x18001f9cc`
- `0x1800222d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007331`
- `msvcrt!_wcsicmp` at `0x180007331`
- `KERNEL32!LocalFree` at `0x18000739c`
- `KERNEL32!LocalFree` at `0x1800073c3`
- `KERNEL32!LocalFree` at `0x18000739c`
- `KERNEL32!LocalFree` at `0x1800073c3`
- `USER32!SendMessageW` at `0x1800072f8`
- `USER32!SendMessageW` at `0x180007318`
- `USER32!SendMessageW` at `0x1800073b7`
- `USER32!SendMessageW` at `0x1800073d0`
- `USER32!SendMessageW` at `0x1800073e7`
- `USER32!SendMessageW` at `0x1800072f8`
- `USER32!SendMessageW` at `0x180007318`
- `USER32!SendMessageW` at `0x1800073b7`
- `USER32!SendMessageW` at `0x1800073d0`
- `USER32!SendMessageW` at `0x1800073e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _AddRegKeysToLogTypeCombo(HWND hWnd, HKEY *this, wchar_t *Source, const unsigned __int16 *Src, int a5)
{
  unsigned int i; // r14d
  unsigned int v10; // edi
  int j; // ebx
  LRESULT v12; // rax
  const wchar_t *v13; // rdx
  unsigned __int16 *LogDisplayName; // rdi
  _DWORD *v15; // rax
  LPARAM v16; // rbx
  int v17; // esi
  wchar_t String1[264]; // [rsp+30h] [rbp-268h] BYREF

  for ( i = 0; !(unsigned int)CSafeReg::Enum((CSafeReg *)this, i, String1, 0x105u); ++i )
  {
    if ( a5 )
    {
      v10 = SendMessageW(hWnd, 0x146u, 0, 0);
      for ( j = 1; j < v10; ++j )
      {
        v12 = SendMessageW(hWnd, 0x150u, j, 0);
        v13 = (const wchar_t *)(v12 + 8);
        if ( *(_QWORD *)(v12 + 32) >= 8u )
          v13 = *(const wchar_t **)v13;
        if ( !_wcsicmp(String1, v13) )
          goto LABEL_20;
      }
    }
    LogDisplayName = GetLogDisplayName(*this, Source, Src, String1);
    v15 = operator new(0x28u);
    v16 = (LPARAM)v15;
    if ( v15 )
    {
      *v15 = *Source == 0;
      std::wstring::wstring(v15 + 2, String1);
    }
    else
    {
      v16 = 0;
    }
    if ( v16 )
    {
      if ( LogDisplayName )
      {
        v17 = SendMessageW(hWnd, 0x143u, 0, (LPARAM)LogDisplayName);
        LocalFree(LogDisplayName);
      }
      else
      {
        v17 = SendMessageW(hWnd, 0x143u, 0, (LPARAM)String1);
      }
      SendMessageW(hWnd, 0x151u, v17, v16);
    }
    else if ( LogDisplayName )
    {
      LocalFree(LogDisplayName);
    }
LABEL_20:
    ;
  }
}

```

## disassembly

```asm
0x18000728c  push    rbx
0x18000728e  push    rbp
0x18000728f  push    rsi
0x180007290  push    rdi
0x180007291  push    r12
0x180007293  push    r13
0x180007295  push    r14
0x180007297  push    r15
0x180007299  sub     rsp, 258h
0x1800072a0  mov     rax, cs:__security_cookie
0x1800072a7  xor     rax, rsp
0x1800072aa  mov     [rsp+298h+var_58], rax
0x1800072b2  mov     r13, r9
0x1800072b5  mov     r12, r8
0x1800072b8  mov     r15, rdx
0x1800072bb  mov     rbp, rcx
0x1800072be  xor     esi, esi
0x1800072c0  mov     r14d, esi
0x1800072c3  mov     r9d, 105h; unsigned int
0x1800072c9  lea     r8, [rsp+298h+String1]; unsigned __int16 *
0x1800072ce  mov     edx, r14d; unsigned int
0x1800072d1  mov     rcx, r15; this
0x1800072d4  call    ?Enum@CSafeReg@@QEBAJKPEAGK@Z; CSafeReg::Enum(ulong,ushort *,ulong)
0x1800072d9  test    eax, eax
0x1800072db  jnz     loc_1800073F7
0x1800072e1  cmp     [rsp+298h+arg_20], esi
0x1800072e8  jz      short loc_180007343
0x1800072ea  xor     r9d, r9d; lParam
0x1800072ed  xor     r8d, r8d; wParam
0x1800072f0  mov     edx, 146h; Msg
0x1800072f5  mov     rcx, rbp; hWnd
0x1800072f8  call    cs:__imp_SendMessageW
0x1800072fe  mov     rdi, rax
0x180007301  mov     ebx, 1
0x180007306  cmp     ebx, edi
0x180007308  jnb     short loc_180007343
0x18000730a  movsxd  r8, ebx; wParam
0x18000730d  xor     r9d, r9d; lParam
0x180007310  mov     edx, 150h; Msg
0x180007315  mov     rcx, rbp; hWnd
0x180007318  call    cs:__imp_SendMessageW
0x18000731e  lea     rdx, [rax+8]
0x180007322  cmp     qword ptr [rax+20h], 8
0x180007327  jb      short loc_18000732C
0x180007329  mov     rdx, [rdx]; String2
0x18000732c  lea     rcx, [rsp+298h+String1]; String1
0x180007331  call    cs:__imp__wcsicmp
0x180007337  test    eax, eax
0x180007339  jz      loc_1800073EF
0x18000733f  inc     ebx
0x180007341  jmp     short loc_180007306
0x180007343  lea     r9, [rsp+298h+String1]; unsigned __int16 *
0x180007348  mov     r8, r13; Src
0x18000734b  mov     rdx, r12; Source
0x18000734e  mov     rcx, [r15]; HKEY
0x180007351  call    ?GetLogDisplayName@@YAPEAGPEAUHKEY__@@PEBG11@Z; GetLogDisplayName(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180007356  mov     rdi, rax
0x180007359  mov     ecx, 28h ; '('; Size
0x18000735e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007363  mov     rbx, rax
0x180007366  mov     [rsp+298h+var_278], rax
0x18000736b  test    rax, rax
0x18000736e  jz      short loc_18000738C
0x180007370  mov     ecx, esi
0x180007372  cmp     [r12], si
0x180007377  setz    cl
0x18000737a  mov     [rax], ecx
0x18000737c  lea     rcx, [rax+8]
0x180007380  lea     rdx, [rsp+298h+String1]
0x180007385  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000738a  jmp     short loc_18000738F
0x18000738c  mov     rbx, rsi
0x18000738f  test    rbx, rbx
0x180007392  jnz     short loc_1800073A4
0x180007394  test    rdi, rdi
0x180007397  jz      short loc_1800073EF
0x180007399  mov     rcx, rdi; hMem
0x18000739c  call    cs:__imp_LocalFree
0x1800073a2  jmp     short loc_1800073EF
0x1800073a4  xor     r8d, r8d; wParam
0x1800073a7  mov     edx, 143h; Msg
0x1800073ac  mov     rcx, rbp; hWnd
0x1800073af  test    rdi, rdi
0x1800073b2  jz      short loc_1800073CB
0x1800073b4  mov     r9, rdi; lParam
0x1800073b7  call    cs:__imp_SendMessageW
0x1800073bd  mov     rsi, rax
0x1800073c0  mov     rcx, rdi; hMem
0x1800073c3  call    cs:__imp_LocalFree
0x1800073c9  jmp     short loc_1800073D9
0x1800073cb  lea     r9, [rsp+298h+String1]; lParam
0x1800073d0  call    cs:__imp_SendMessageW
0x1800073d6  mov     rsi, rax
0x1800073d9  movsxd  r8, esi; wParam
0x1800073dc  mov     r9, rbx; lParam
0x1800073df  mov     edx, 151h; Msg
0x1800073e4  mov     rcx, rbp; hWnd
0x1800073e7  call    cs:__imp_SendMessageW
0x1800073ed  xor     esi, esi
0x1800073ef  inc     r14d
0x1800073f2  jmp     loc_1800072C3
0x1800073f7  mov     rcx, [rsp+298h+var_58]
0x1800073ff  xor     rcx, rsp; StackCookie
0x180007402  call    __security_check_cookie
0x180007407  add     rsp, 258h
0x18000740e  pop     r15
0x180007410  pop     r14
0x180007412  pop     r13
0x180007414  pop     r12
0x180007416  pop     rdi
0x180007417  pop     rsi
0x180007418  pop     rbp
0x180007419  pop     rbx
0x18000741a  retn
```
