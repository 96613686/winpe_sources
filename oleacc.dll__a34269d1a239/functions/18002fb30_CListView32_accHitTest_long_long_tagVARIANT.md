# CListView32::accHitTest(long,long,tagVARIANT *)

- ea: `0x18002fb30`
- end: `0x18002fcb0`
- name: `?accHitTest@CListView32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(CListView32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x18002fb30`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002fc8a`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18002fc8a`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fbec`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fc26`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fbec`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18002fc26`
- `USER32!ScreenToClient` at `0x18002fc04`
- `USER32!ScreenToClient` at `0x18002fc04`

## pseudocode

```c
int __fastcall CListView32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  int result; // eax
  char *v9; // rax
  __int64 v10; // rdi
  HWND v11; // rcx
  int v12; // ebp
  HANDLE v13; // rdx
  HANDLE hProcess; // [rsp+40h] [rbp-48h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp-40h] BYREF
  int Buffer; // [rsp+90h] [rbp+8h] BYREF

  hProcess = 0;
  Buffer = 0;
  Point = 0;
  (*((void (__fastcall **)(HWND *))*this + 29))(this);
  result = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !result && a4->vt == 3 && !a4->lVal )
  {
    v9 = (char *)SharedAlloc(0x18u, this[10], &hProcess);
    v10 = (__int64)v9;
    if ( v9 )
    {
      Buffer = -1;
      WriteProcessMemory(hProcess, v9 + 12, &Buffer, 4u, 0);
      v11 = this[10];
      Point.x = a2;
      Point.y = a3;
      ScreenToClient(v11, &Point);
      WriteProcessMemory(hProcess, (LPVOID)v10, &Point, 8u, 0);
      v12 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x1039u, 0, v10, 0);
      if ( v12 >= 0 )
      {
        ReadProcessMemory(hProcess, (LPCVOID)(v10 + 12), &a4->decVal.8, 4u, 0);
        v13 = hProcess;
        ++a4->lVal;
        SharedFree((void *)v10, v13);
        return 0;
      }
      else
      {
        SharedFree((void *)v10, hProcess);
        return v12;
      }
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002fb30  mov     rax, rsp
0x18002fb33  push    rbx
0x18002fb34  push    rbp
0x18002fb35  push    rdi
0x18002fb36  push    r12
0x18002fb38  push    r14
0x18002fb3a  push    r15
0x18002fb3c  sub     rsp, 58h
0x18002fb40  mov     qword ptr [rax-48h], 0
0x18002fb48  mov     rbx, r9
0x18002fb4b  mov     dword ptr [rax+8], 0
0x18002fb52  mov     ebp, r8d
0x18002fb55  mov     qword ptr [rax-40h], 0
0x18002fb5d  mov     r12d, edx
0x18002fb60  mov     rax, [rcx]
0x18002fb63  mov     r14, rcx
0x18002fb66  mov     rax, [rax+0E8h]
0x18002fb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb72  mov     r9, rbx; struct tagVARIANT *
0x18002fb75  mov     r8d, ebp; int
0x18002fb78  mov     edx, r12d; int
0x18002fb7b  mov     rcx, r14; this
0x18002fb7e  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x18002fb83  test    eax, eax
0x18002fb85  jnz     loc_18002FCA2
0x18002fb8b  cmp     word ptr [rbx], 3
0x18002fb8f  jnz     loc_18002FCA2
0x18002fb95  cmp     [rbx+8], eax
0x18002fb98  jnz     loc_18002FCA2
0x18002fb9e  mov     rdx, [r14+50h]; HWND
0x18002fba2  lea     r8, [rsp+88h+hProcess]; void **
0x18002fba7  lea     ecx, [rax+18h]; dwSize
0x18002fbaa  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18002fbaf  mov     rdi, rax
0x18002fbb2  test    rax, rax
0x18002fbb5  jnz     short loc_18002FBC1
0x18002fbb7  mov     eax, 8007000Eh
0x18002fbbc  jmp     loc_18002FCA2
0x18002fbc1  mov     rcx, [rsp+88h+hProcess]; hProcess
0x18002fbc6  lea     r8, [rsp+88h+Buffer]; lpBuffer
0x18002fbce  mov     r9d, 4; nSize
0x18002fbd4  mov     [rsp+88h+Buffer], 0FFFFFFFFh
0x18002fbdf  lea     rdx, [rax+0Ch]; lpBaseAddress
0x18002fbe3  mov     [rsp+88h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002fbec  call    cs:__imp_WriteProcessMemory
0x18002fbf2  mov     rcx, [r14+50h]; hWnd
0x18002fbf6  lea     rdx, [rsp+88h+Point]; lpPoint
0x18002fbfb  mov     [rsp+88h+Point.x], r12d
0x18002fc00  mov     [rsp+88h+Point.y], ebp
0x18002fc04  call    cs:__imp_ScreenToClient
0x18002fc0a  mov     rcx, [rsp+88h+hProcess]; hProcess
0x18002fc0f  lea     r8, [rsp+88h+Point]; lpBuffer
0x18002fc14  mov     r9d, 8; nSize
0x18002fc1a  mov     [rsp+88h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18002fc23  mov     rdx, rdi; lpBaseAddress
0x18002fc26  call    cs:__imp_WriteProcessMemory
0x18002fc2c  mov     r8, [r14+50h]; HWND
0x18002fc30  mov     r9d, 1039h; unsigned int
0x18002fc36  mov     [rsp+88h+var_58], 0; __int64 *
0x18002fc3f  xor     edx, edx; bool
0x18002fc41  mov     [rsp+88h+var_60], rdi; __int64
0x18002fc46  mov     rcx, r14; this
0x18002fc49  mov     [rsp+88h+lpNumberOfBytesWritten], 0; unsigned __int64
0x18002fc52  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18002fc57  mov     ebp, eax
0x18002fc59  test    eax, eax
0x18002fc5b  jns     short loc_18002FC6E
0x18002fc5d  mov     rdx, [rsp+88h+hProcess]; hProcess
0x18002fc62  mov     rcx, rdi; lpAddress
0x18002fc65  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002fc6a  mov     eax, ebp
0x18002fc6c  jmp     short loc_18002FCA2
0x18002fc6e  mov     rcx, [rsp+88h+hProcess]; hProcess
0x18002fc73  lea     r8, [rbx+8]; lpBuffer
0x18002fc77  mov     r9d, 4; nSize
0x18002fc7d  mov     [rsp+88h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18002fc86  lea     rdx, [rdi+0Ch]; lpBaseAddress
0x18002fc8a  call    cs:__imp_ReadProcessMemory
0x18002fc90  mov     rdx, [rsp+88h+hProcess]; hProcess
0x18002fc95  mov     rcx, rdi; lpAddress
0x18002fc98  inc     dword ptr [rbx+8]
0x18002fc9b  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18002fca0  xor     eax, eax
0x18002fca2  add     rsp, 58h
0x18002fca6  pop     r15
0x18002fca8  pop     r14
0x18002fcaa  pop     r12
0x18002fcac  pop     rdi
0x18002fcad  pop     rbp
0x18002fcae  pop     rbx
0x18002fcaf  retn
```
