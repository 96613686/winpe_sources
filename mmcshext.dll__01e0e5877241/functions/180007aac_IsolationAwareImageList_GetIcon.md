# IsolationAwareImageList_GetIcon

- ea: `0x180007aac`
- end: `0x180007b80`
- name: `IsolationAwareImageList_GetIcon`
- size: `212`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007420`
- `0x18000879c`

## callees

- `0x180006a44`
- `0x180007918`
- `0x180007aac`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180007b72`
- `KERNEL32!SetLastError` at `0x18000ad42`
- `KERNEL32!SetLastError` at `0x180007b72`
- `KERNEL32!SetLastError` at `0x18000ad42`
- `KERNEL32!DeactivateActCtx` at `0x180007b66`
- `KERNEL32!DeactivateActCtx` at `0x18000ad36`
- `KERNEL32!DeactivateActCtx` at `0x180007b66`
- `KERNEL32!DeactivateActCtx` at `0x18000ad36`
- `KERNEL32!GetLastError` at `0x180007b51`
- `KERNEL32!GetLastError` at `0x18000ad22`
- `KERNEL32!GetLastError` at `0x180007b51`
- `KERNEL32!GetLastError` at `0x18000ad22`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_GetIcon(__int64 a1)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(_QWORD, _QWORD, _QWORD); // rbx
  FARPROC v5; // rax
  int v6; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))`IsolationAwareImageList_GetIcon'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_GetIcon");
    v3 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v5;
    if ( !v5 )
      goto LABEL_9;
    `IsolationAwareImageList_GetIcon'::`2'::s_pfn = (__int64)v5;
  }
  v2 = v3(a1, 0, 0);
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v2 )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x180007aac  mov     rax, rsp
0x180007aaf  mov     [rax+8], rbx
0x180007ab3  mov     [rax+10h], rsi
0x180007ab7  push    rdi
0x180007ab8  sub     rsp, 30h
0x180007abc  mov     rsi, rcx
0x180007abf  xor     edi, edi
0x180007ac1  mov     [rax-18h], rdi
0x180007ac5  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_GetIcon@@9@4P6APEAUHICON__@@PEAU_IMAGELIST@@HI@ZEA; HICON__ * (*`IsolationAwareImageList_GetIcon'::`2'::s_pfn)(_IMAGELIST *,int,uint)
0x180007acc  mov     [rax+20h], rdi
0x180007ad0  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, edi
0x180007ad6  jnz     short loc_180007AFF
0x180007ad8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180007ade  jnz     short loc_180007AFF
0x180007ae0  lea     rcx, [rax+20h]; lpCookie
0x180007ae4  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180007ae9  test    eax, eax
0x180007aeb  jnz     short loc_180007AFF
0x180007aed  xor     eax, eax
0x180007aef  mov     rbx, [rsp+38h+arg_0]
0x180007af4  mov     rsi, [rsp+38h+arg_8]
0x180007af9  add     rsp, 30h
0x180007afd  pop     rdi
0x180007afe  retn
0x180007aff  test    rbx, rbx
0x180007b02  jnz     short loc_180007B1F
0x180007b04  lea     rcx, aImagelistGetic; "ImageList_GetIcon"
0x180007b0b  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x180007b10  mov     rbx, rax
0x180007b13  test    rax, rax
0x180007b16  jz      short loc_180007B37
0x180007b18  mov     cs:?s_pfn@?1??IsolationAwareImageList_GetIcon@@9@4P6APEAUHICON__@@PEAU_IMAGELIST@@HI@ZEA, rax; HICON__ * (*`IsolationAwareImageList_GetIcon'::`2'::s_pfn)(_IMAGELIST *,int,uint)
0x180007b1f  xor     r8d, r8d
0x180007b22  xor     edx, edx
0x180007b24  mov     rcx, rsi
0x180007b27  mov     rax, rbx
0x180007b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b2f  mov     rdi, rax
0x180007b32  mov     [rsp+38h+var_18], rax
0x180007b37  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180007b3e  jz      short loc_180007B49
0x180007b40  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180007b47  jnz     short loc_180007B78
0x180007b49  test    rdi, rdi
0x180007b4c  jnz     short loc_180007B5B
0x180007b4e  lea     esi, [rdi+1]
0x180007b51  call    cs:__imp_GetLastError
0x180007b57  mov     ebx, eax
0x180007b59  jmp     short loc_180007B5F
0x180007b5b  xor     esi, esi
0x180007b5d  xor     ebx, ebx
0x180007b5f  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x180007b64  xor     ecx, ecx; dwFlags
0x180007b66  call    cs:__imp_DeactivateActCtx
0x180007b6c  test    esi, esi
0x180007b6e  jz      short loc_180007B78
0x180007b70  mov     ecx, ebx; dwErrCode
0x180007b72  call    cs:__imp_SetLastError
0x180007b78  mov     rax, rdi
0x180007b7b  jmp     loc_180007AEF
0x18000acf9  push    rbx
0x18000acfb  push    rbp
0x18000acfc  push    rdi
0x18000acfd  sub     rsp, 20h
0x18000ad01  mov     rbp, rdx
0x18000ad04  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ad0b  jz      short loc_18000AD16
0x18000ad0d  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ad14  jnz     short loc_18000AD49
0x18000ad16  cmp     qword ptr [rbp+20h], 0
0x18000ad1b  jnz     short loc_18000AD2C
0x18000ad1d  mov     edi, 1
0x18000ad22  call    cs:__imp_GetLastError
0x18000ad28  mov     ebx, eax
0x18000ad2a  jmp     short loc_18000AD30
0x18000ad2c  xor     edi, edi
0x18000ad2e  xor     ebx, ebx
0x18000ad30  mov     rdx, [rbp+58h]; ulCookie
0x18000ad34  xor     ecx, ecx; dwFlags
0x18000ad36  call    cs:__imp_DeactivateActCtx
0x18000ad3c  test    edi, edi
0x18000ad3e  jz      short loc_18000AD49
0x18000ad40  mov     ecx, ebx; dwErrCode
0x18000ad42  call    cs:__imp_SetLastError
0x18000ad48  nop
0x18000ad49  add     rsp, 20h
0x18000ad4d  pop     rdi
0x18000ad4e  pop     rbp
0x18000ad4f  pop     rbx
0x18000ad50  retn
```
