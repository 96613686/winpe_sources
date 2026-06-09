# ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<13565952,134217728>>::StartWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800d2250`
- end: `0x1800d233e`
- name: `?StartWindowProc@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0MPAAAA@$0IAAAAAA@@2@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `238`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800d2250`
- `0x1800ee708`
- `0x1800ee780`
- `0x1800ee81c`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800d2284`
- `KERNEL32!GetCurrentThreadId` at `0x1800d2284`
- `KERNEL32!LeaveCriticalSection` at `0x1800d22bf`
- `KERNEL32!LeaveCriticalSection` at `0x1800d22bf`
- `KERNEL32!EnterCriticalSection` at `0x1800d2272`
- `KERNEL32!EnterCriticalSection` at `0x1800d2272`
- `USER32!SetWindowLongPtrW` at `0x1800d2317`
- `USER32!SetWindowLongPtrW` at `0x1800d2317`

## pseudocode

```c
__int64 __fastcall ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<13565952,134217728>>::StartWindowProc(
        HWND hWnd,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  size_t v8; // rdi
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rax
  void *v13; // rbx
  AtlThunkData_t *Data; // rax
  WNDPROC v15; // rbx

  v8 = 0;
  EnterCriticalSection(&stru_18021D030);
  v9 = qword_18021D088;
  if ( qword_18021D088 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = 0;
    while ( v9 )
    {
      if ( *(_DWORD *)(v9 + 8) == CurrentThreadId )
      {
        if ( v11 )
          *(_QWORD *)(v11 + 16) = *(_QWORD *)(v9 + 16);
        else
          qword_18021D088 = *(_QWORD *)(v9 + 16);
        v8 = *(_QWORD *)v9;
        break;
      }
      v11 = v9;
      v9 = *(_QWORD *)(v9 + 16);
    }
  }
  LeaveCriticalSection(&stru_18021D030);
  v12 = *(_QWORD *)v8;
  *(_QWORD *)(v8 + 8) = hWnd;
  v13 = (void *)(*(__int64 (__fastcall **)(size_t))(v12 + 8))(v8);
  Data = *(AtlThunkData_t **)(v8 + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(v8 + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v13, v8);
  v15 = AtlThunk_DataToCode(*(AtlThunkData_t **)(v8 + 40));
  SetWindowLongPtrW(hWnd, -4, (LONG_PTR)v15);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v15)(hWnd, a2, a3, a4);
}

```

## disassembly

```asm
0x1800d2250  push    rbx
0x1800d2252  push    rbp
0x1800d2253  push    rsi
0x1800d2254  push    rdi
0x1800d2255  push    r14
0x1800d2257  push    r15
0x1800d2259  sub     rsp, 38h
0x1800d225d  mov     rsi, rcx
0x1800d2260  mov     rbp, r9
0x1800d2263  lea     rcx, stru_18021D030; lpCriticalSection
0x1800d226a  mov     r14, r8
0x1800d226d  mov     r15d, edx
0x1800d2270  xor     edi, edi
0x1800d2272  call    cs:__imp_EnterCriticalSection
0x1800d2278  mov     rbx, cs:qword_18021D088
0x1800d227f  test    rbx, rbx
0x1800d2282  jz      short loc_1800D22B8
0x1800d2284  call    cs:__imp_GetCurrentThreadId
0x1800d228a  xor     r8d, r8d
0x1800d228d  test    rbx, rbx
0x1800d2290  jz      short loc_1800D22B8
0x1800d2292  mov     rcx, [rbx+10h]
0x1800d2296  cmp     [rbx+8], eax
0x1800d2299  jz      short loc_1800D22A3
0x1800d229b  mov     r8, rbx
0x1800d229e  mov     rbx, rcx
0x1800d22a1  jmp     short loc_1800D228D
0x1800d22a3  test    r8, r8
0x1800d22a6  jnz     short loc_1800D22B1
0x1800d22a8  mov     cs:qword_18021D088, rcx
0x1800d22af  jmp     short loc_1800D22B5
0x1800d22b1  mov     [r8+10h], rcx
0x1800d22b5  mov     rdi, [rbx]
0x1800d22b8  lea     rcx, stru_18021D030; lpCriticalSection
0x1800d22bf  call    cs:__imp_LeaveCriticalSection
0x1800d22c5  mov     rax, [rdi]
0x1800d22c8  mov     rcx, rdi
0x1800d22cb  mov     [rdi+8], rsi
0x1800d22cf  mov     rax, [rax+8]
0x1800d22d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d22d8  mov     rbx, rax
0x1800d22db  mov     rax, [rdi+28h]
0x1800d22df  test    rax, rax
0x1800d22e2  jnz     short loc_1800D22F2
0x1800d22e4  call    AtlThunk_AllocateData
0x1800d22e9  mov     [rdi+28h], rax
0x1800d22ed  test    rax, rax
0x1800d22f0  jz      short loc_1800D2300
0x1800d22f2  mov     r8, rdi; FirstParameter
0x1800d22f5  mov     rdx, rbx; Proc
0x1800d22f8  mov     rcx, rax; Thunk
0x1800d22fb  call    AtlThunk_InitData
0x1800d2300  mov     rcx, [rdi+28h]; AtlThunkData_t *
0x1800d2304  call    AtlThunk_DataToCode
0x1800d2309  mov     r8, rax; dwNewLong
0x1800d230c  mov     edx, 0FFFFFFFCh; nIndex
0x1800d2311  mov     rcx, rsi; hWnd
0x1800d2314  mov     rbx, rax
0x1800d2317  call    cs:__imp_SetWindowLongPtrW
0x1800d231d  mov     r9, rbp
0x1800d2320  mov     r8, r14
0x1800d2323  mov     edx, r15d
0x1800d2326  mov     rcx, rsi
0x1800d2329  mov     rax, rbx
0x1800d232c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2331  add     rsp, 38h
0x1800d2335  pop     r15
0x1800d2337  pop     r14
0x1800d2339  pop     rdi
0x1800d233a  pop     rsi
0x1800d233b  pop     rbp
0x1800d233c  pop     rbx
0x1800d233d  retn
```
