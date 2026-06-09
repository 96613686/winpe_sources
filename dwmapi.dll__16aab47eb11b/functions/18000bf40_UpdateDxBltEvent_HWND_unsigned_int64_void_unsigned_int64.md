# UpdateDxBltEvent(HWND__ *,unsigned __int64,void * *,unsigned __int64 *)

- ea: `0x18000bf40`
- end: `0x18000bfec`
- name: `?UpdateDxBltEvent@@YAJPEAUHWND__@@_KPEAPEAXPEA_K@Z`
- size: `172`
- prototype: `__int64 __fastcall(HWND, unsigned __int64, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180002200`

## callees

- `0x180003370`
- `0x180005534`
- `0x18000bf40`
- `0x180013570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bf62`

## pseudocode

```c
__int64 __fastcall UpdateDxBltEvent(HWND a1, __int64 a2, void **a3, unsigned __int64 *a4)
{
  int inserted; // eax
  unsigned int v9; // ebx
  struct CDwmHwndData *v10; // rdi
  void **v11; // rsi
  unsigned int v12; // edx
  struct CDwmHwndData *v14; // [rsp+20h] [rbp-48h] BYREF

  EnterCriticalSection(&CDwmHwndData::s_cs);
  v14 = 0;
  inserted = CDwmHwndData::InsertElement(a1, &v14);
  v9 = inserted;
  if ( inserted < 0 )
  {
    v12 = 446;
    goto LABEL_7;
  }
  v10 = v14;
  v11 = (void **)((char *)v14 + 24);
  if ( !*((_QWORD *)v14 + 3) )
  {
    inserted = CreateDxBltEvent(a1, (void **)v14 + 3, (unsigned __int64 *)v14 + 4);
    v9 = inserted;
    if ( inserted < 0 )
    {
      v12 = 452;
LABEL_7:
      DoStackCaptureDirect(inserted, v12);
      goto LABEL_8;
    }
  }
  *((_QWORD *)v10 + 5) = a2;
  *a3 = *v11;
  *a4 = *((_QWORD *)v10 + 4);
LABEL_8:
  LeaveCriticalSection(&CDwmHwndData::s_cs);
  return v9;
}

```

## disassembly

```asm
0x18000bf40  push    rbx
0x18000bf42  push    rbp
0x18000bf43  push    rsi
0x18000bf44  push    rdi
0x18000bf45  push    r12
0x18000bf47  push    r14
0x18000bf49  push    r15
0x18000bf4b  sub     rsp, 30h
0x18000bf4f  mov     rbp, rcx
0x18000bf52  mov     r14, r9
0x18000bf55  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x18000bf5c  mov     r15, r8
0x18000bf5f  mov     r12, rdx
0x18000bf62  call    cs:__imp_EnterCriticalSection
0x18000bf68  lea     rdx, [rsp+68h+var_48]; struct CDwmHwndData **
0x18000bf6d  mov     [rsp+68h+var_48], 0
0x18000bf76  mov     rcx, rbp; HWND
0x18000bf79  call    ?InsertElement@CDwmHwndData@@SAJPEAUHWND__@@PEAPEAV1@@Z; CDwmHwndData::InsertElement(HWND__ *,CDwmHwndData * *)
0x18000bf7e  mov     ebx, eax
0x18000bf80  test    eax, eax
0x18000bf82  js      short loc_18000BFC2
0x18000bf84  mov     rdi, [rsp+68h+var_48]
0x18000bf89  lea     rsi, [rdi+18h]
0x18000bf8d  cmp     qword ptr [rsi], 0
0x18000bf91  jnz     short loc_18000BFAF
0x18000bf93  lea     r8, [rdi+20h]; unsigned __int64 *
0x18000bf97  mov     rdx, rsi; void **
0x18000bf9a  mov     rcx, rbp; HWND
0x18000bf9d  call    ?CreateDxBltEvent@@YAJQEAUHWND__@@PEAPEAXPEA_K@Z; CreateDxBltEvent(HWND__ * const,void * *,unsigned __int64 *)
0x18000bfa2  mov     ebx, eax
0x18000bfa4  test    eax, eax
0x18000bfa6  jns     short loc_18000BFAF
0x18000bfa8  mov     edx, 1C4h
0x18000bfad  jmp     short loc_18000BFC7
0x18000bfaf  mov     [rdi+28h], r12
0x18000bfb3  mov     rax, [rsi]
0x18000bfb6  mov     [r15], rax
0x18000bfb9  mov     rax, [rdi+20h]
0x18000bfbd  mov     [r14], rax
0x18000bfc0  jmp     short loc_18000BFCE
0x18000bfc2  mov     edx, 1BEh; unsigned int
0x18000bfc7  mov     ecx, eax; int
0x18000bfc9  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000bfce  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x18000bfd5  call    cs:__imp_LeaveCriticalSection
0x18000bfdb  mov     eax, ebx
0x18000bfdd  add     rsp, 30h
0x18000bfe1  pop     r15
0x18000bfe3  pop     r14
0x18000bfe5  pop     r12
0x18000bfe7  pop     rdi
0x18000bfe8  pop     rsi
0x18000bfe9  pop     rbp
0x18000bfea  pop     rbx
0x18000bfeb  retn
```
