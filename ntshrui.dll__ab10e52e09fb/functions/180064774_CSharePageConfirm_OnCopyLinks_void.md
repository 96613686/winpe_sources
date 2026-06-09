# CSharePageConfirm::_OnCopyLinks(void)

- ea: `0x180064774`
- end: `0x180064883`
- name: `?_OnCopyLinks@CSharePageConfirm@@AEAAXXZ`
- size: `271`
- prototype: `void __fastcall(CSharePageConfirm *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064a58`

## callees

- `0x180013220`
- `0x1800645b0`
- `0x180064774`
- `0x180072bb8`
- `0x180072ff4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180064856`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180064856`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800647f6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800647f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006485f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006485f`
- `KERNEL32!GlobalLock` at `0x180064807`
- `KERNEL32!GlobalLock` at `0x180064807`
- `KERNEL32!GlobalUnlock` at `0x180064823`
- `KERNEL32!GlobalUnlock` at `0x180064823`
- `USER32!SetClipboardData` at `0x180064845`
- `USER32!SetClipboardData` at `0x180064845`
- `USER32!EmptyClipboard` at `0x180064837`
- `USER32!EmptyClipboard` at `0x180064837`
- `USER32!OpenClipboard` at `0x18006482d`
- `USER32!OpenClipboard` at `0x18006482d`
- `USER32!CloseClipboard` at `0x18006484b`
- `USER32!CloseClipboard` at `0x18006484b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSharePageConfirm::_OnCopyLinks(HWND *this, __int64 a2)
{
  unsigned int v3; // edx
  unsigned __int16 *v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rsi
  HGLOBAL v7; // rax
  void *v8; // rbx
  unsigned __int16 *v9; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  if ( (int)GetShellItemsFromResultList(this[2] + 16, a2, &v10) >= 0 )
  {
    pv = 0;
    v3 = v10 ? *(_DWORD *)v10 : 0;
    if ( (int)FormatPathsAsLinks(*(struct IShellItem ***)(v10 + 8), v3, (unsigned __int16 **)&pv) >= 0 )
    {
      v4 = (unsigned __int16 *)pv;
      v5 = -1;
      do
        ++v5;
      while ( *((_WORD *)pv + v5) );
      v6 = v5 + 1;
      v7 = GlobalAlloc(0x2042u, 2 * (v5 + 1));
      v8 = v7;
      if ( v7 )
      {
        v9 = (unsigned __int16 *)GlobalLock(v7);
        if ( v9 && (StringCchCopyW(v9, v6, v4), GlobalUnlock(v8), OpenClipboard(this[1])) )
        {
          EmptyClipboard();
          SetClipboardData(0xDu, v8);
          CloseClipboard();
        }
        else
        {
          GlobalFree(v8);
        }
      }
      CoTaskMemFree(v4);
    }
  }
  CDPA_Base<IShellItem,CTContainer_PolicyRelease<IShellItem>>::~CDPA_Base<IShellItem,CTContainer_PolicyRelease<IShellItem>>(&v10);
}

```

## disassembly

```asm
0x180064774  mov     rax, rsp
0x180064777  mov     [rax+18h], rbx
0x18006477b  mov     [rax+20h], rbp
0x18006477f  push    rsi
0x180064780  push    rdi
0x180064781  push    r14
0x180064783  sub     rsp, 20h
0x180064787  mov     rbp, rcx
0x18006478a  xor     r14d, r14d
0x18006478d  mov     [rax+8], r14
0x180064791  mov     rcx, [rcx+10h]
0x180064795  add     rcx, 40h ; '@'
0x180064799  lea     r8, [rax+8]
0x18006479d  call    ?GetShellItemsFromResultList@@YAJAEBV?$CDPARelease@VCShareItemResult@@V?$CTContainer_PolicyRelease@VCShareItemResult@@@@@@W4_SHARE_OPERATION_RESULT@@AEAV?$CDPARelease@UIShellItem@@V?$CTContainer_PolicyRelease@UIShellItem@@@@@@@Z; GetShellItemsFromResultList(CDPARelease<CShareItemResult,CTContainer_PolicyRelease<CShareItemResult>> const &,_SHARE_OPERATION_RESULT,CDPARelease<IShellItem,CTContainer_PolicyRelease<IShellItem>> &)
0x1800647a2  test    eax, eax
0x1800647a4  js      loc_180064866
0x1800647aa  mov     [rsp+38h+pv], r14
0x1800647af  mov     rcx, [rsp+38h+arg_0]
0x1800647b4  test    rcx, rcx
0x1800647b7  jz      short loc_1800647BD
0x1800647b9  mov     edx, [rcx]
0x1800647bb  jmp     short loc_1800647C0
0x1800647bd  mov     edx, r14d; unsigned int
0x1800647c0  lea     r8, [rsp+38h+pv]; unsigned __int16 **
0x1800647c5  mov     rcx, [rcx+8]; struct IShellItem **
0x1800647c9  call    ?FormatPathsAsLinks@@YAJPEAPEAUIShellItem@@KPEAPEAG@Z; FormatPathsAsLinks(IShellItem * *,ulong,ushort * *)
0x1800647ce  test    eax, eax
0x1800647d0  js      loc_180064866
0x1800647d6  mov     rdi, [rsp+38h+pv]
0x1800647db  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800647df  inc     rax
0x1800647e2  cmp     [rdi+rax*2], r14w
0x1800647e7  jnz     short loc_1800647DF
0x1800647e9  lea     rsi, [rax+1]
0x1800647ed  lea     rdx, [rsi+rsi]; dwBytes
0x1800647f1  mov     ecx, 2042h; uFlags
0x1800647f6  call    cs:__imp_GlobalAlloc
0x1800647fc  mov     rbx, rax
0x1800647ff  test    rax, rax
0x180064802  jz      short loc_18006485C
0x180064804  mov     rcx, rax; hMem
0x180064807  call    cs:__imp_GlobalLock
0x18006480d  test    rax, rax
0x180064810  jz      short loc_180064853
0x180064812  mov     r8, rdi; unsigned __int16 *
0x180064815  mov     rdx, rsi; unsigned __int64
0x180064818  mov     rcx, rax; unsigned __int16 *
0x18006481b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064820  mov     rcx, rbx; hMem
0x180064823  call    cs:__imp_GlobalUnlock
0x180064829  mov     rcx, [rbp+8]; hWndNewOwner
0x18006482d  call    cs:__imp_OpenClipboard
0x180064833  test    eax, eax
0x180064835  jz      short loc_180064853
0x180064837  call    cs:__imp_EmptyClipboard
0x18006483d  mov     rdx, rbx; hMem
0x180064840  mov     ecx, 0Dh; uFormat
0x180064845  call    cs:__imp_SetClipboardData
0x18006484b  call    cs:__imp_CloseClipboard
0x180064851  jmp     short loc_18006485C
0x180064853  mov     rcx, rbx; hMem
0x180064856  call    cs:__imp_GlobalFree
0x18006485c  mov     rcx, rdi; pv
0x18006485f  call    cs:__imp_CoTaskMemFree
0x180064865  nop
0x180064866  lea     rcx, [rsp+38h+arg_0]
0x18006486b  call    ??1?$CDPA_Base@UIShellItem@@V?$CTContainer_PolicyRelease@UIShellItem@@@@@@QEAA@XZ; CDPA_Base<IShellItem,CTContainer_PolicyRelease<IShellItem>>::~CDPA_Base<IShellItem,CTContainer_PolicyRelease<IShellItem>>(void)
0x180064870  mov     rbx, [rsp+38h+arg_10]
0x180064875  mov     rbp, [rsp+38h+arg_18]
0x18006487a  add     rsp, 20h
0x18006487e  pop     r14
0x180064880  pop     rdi
0x180064881  pop     rsi
0x180064882  retn
```
