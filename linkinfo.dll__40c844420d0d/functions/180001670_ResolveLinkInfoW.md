# ResolveLinkInfoW

- ea: `0x180001670`
- end: `0x18000176c`
- name: `ResolveLinkInfoW`
- size: `252`
- prototype: `__int64 __fastcall(struct _ilinkinfoW *, unsigned __int16 *, unsigned int, HWND, __int64, struct _ilinkinfoW **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800055e0`

## callees

- `0x180001670`
- `0x180001780`
- `0x18000535c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000170f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000170f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180001722`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x180001722`

## pseudocode

```c
int __fastcall ResolveLinkInfoW(
        struct _ilinkinfoW *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        HWND a4,
        _DWORD *a5,
        struct _ilinkinfoW **a6)
{
  int result; // eax
  unsigned int v11[18]; // [rsp+30h] [rbp-48h] BYREF

  if ( a2
    && (a3 & 0xFFFFFFC0) == 0
    && ((a3 & 4) == 0 || IsWindow(a4))
    && a5
    && ((a3 & 0x10) == 0 || a6)
    && ((a3 & 2) == 0 || (a3 & 1) != 0) )
  {
    v11[0] = 0;
    *a5 = 0;
    result = ResolveILinkInfo(a1, a2, a3, a3, a4, v11);
    if ( result )
    {
      *a5 |= v11[0];
      if ( (a3 & 0x10) != 0 )
      {
        result = UpdateILinkInfo(a1, a2, v11, a6);
        if ( result )
          *a5 |= v11[0];
      }
    }
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001670  push    rbx
0x180001672  push    rbp
0x180001673  push    rsi
0x180001674  push    rdi
0x180001675  push    r14
0x180001677  push    r15
0x180001679  sub     rsp, 48h
0x18000167d  mov     r15, r9
0x180001680  mov     ebx, r8d
0x180001683  mov     rsi, rdx
0x180001686  mov     rdi, rcx
0x180001689  test    rdx, rdx
0x18000168c  jz      short loc_18000170A
0x18000168e  test    ebx, 0FFFFFFC0h
0x180001694  jnz     short loc_18000170A
0x180001696  test    bl, 4
0x180001699  jnz     loc_18000171F
0x18000169f  mov     r14, [rsp+78h+arg_20]
0x1800016a7  test    r14, r14
0x1800016aa  jz      short loc_18000170A
0x1800016ac  mov     ebp, ebx
0x1800016ae  and     ebp, 10h
0x1800016b1  jnz     loc_180001737
0x1800016b7  test    bl, 2
0x1800016ba  jz      short loc_1800016C1
0x1800016bc  test    bl, 1
0x1800016bf  jz      short loc_18000170A
0x1800016c1  lea     rax, [rsp+78h+var_48]
0x1800016c6  mov     [rsp+78h+var_48], 0
0x1800016ce  mov     [rsp+78h+var_50], rax; unsigned int *
0x1800016d3  mov     r9d, ebx; unsigned int
0x1800016d6  mov     rdx, rsi; unsigned __int16 *
0x1800016d9  mov     [rsp+78h+var_58], r15; HWND
0x1800016de  mov     rcx, rdi; struct _ilinkinfoW *
0x1800016e1  mov     dword ptr [r14], 0
0x1800016e8  call    ?ResolveILinkInfo@@YAHPEBU_ilinkinfoW@@PEAGHKPEAUHWND__@@PEAK@Z; ResolveILinkInfo(_ilinkinfoW const *,ushort *,int,ulong,HWND__ *,ulong *)
0x1800016ed  test    eax, eax
0x1800016ef  jz      short loc_1800016FC
0x1800016f1  mov     ecx, [rsp+78h+var_48]
0x1800016f5  or      [r14], ecx
0x1800016f8  test    ebp, ebp
0x1800016fa  jnz     short loc_180001747
0x1800016fc  add     rsp, 48h
0x180001700  pop     r15
0x180001702  pop     r14
0x180001704  pop     rdi
0x180001705  pop     rsi
0x180001706  pop     rbp
0x180001707  pop     rbx
0x180001708  retn
0x18000170a  mov     ecx, 57h ; 'W'; dwErrCode
0x18000170f  call    cs:__imp_SetLastError
0x180001716  nop     dword ptr [rax+rax+00h]
0x18000171b  xor     eax, eax
0x18000171d  jmp     short loc_1800016FC
0x18000171f  mov     rcx, r15; hWnd
0x180001722  call    cs:__imp_IsWindow
0x180001729  nop     dword ptr [rax+rax+00h]
0x18000172e  test    eax, eax
0x180001730  jz      short loc_18000170A
0x180001732  jmp     loc_18000169F
0x180001737  cmp     [rsp+78h+arg_28], 0
0x180001740  jz      short loc_18000170A
0x180001742  jmp     loc_1800016B7
0x180001747  mov     r9, [rsp+78h+arg_28]; struct _ilinkinfoW **
0x18000174f  lea     r8, [rsp+78h+var_48]; unsigned int *
0x180001754  mov     rdx, rsi; unsigned __int16 *
0x180001757  mov     rcx, rdi; struct _ilinkinfoW *
0x18000175a  call    ?UpdateILinkInfo@@YAHPEBU_ilinkinfoW@@PEBGPEAKPEAPEAU1@@Z; UpdateILinkInfo(_ilinkinfoW const *,ushort const *,ulong *,_ilinkinfoW * *)
0x18000175f  test    eax, eax
0x180001761  jz      short loc_1800016FC
0x180001763  mov     ecx, [rsp+78h+var_48]
0x180001767  or      [r14], ecx
0x18000176a  jmp     short loc_1800016FC
```
