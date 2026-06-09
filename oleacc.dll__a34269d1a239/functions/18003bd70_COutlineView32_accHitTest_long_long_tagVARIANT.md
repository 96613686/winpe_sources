# COutlineView32::accHitTest(long,long,tagVARIANT *)

- ea: `0x18003bd70`
- end: `0x18003bf07`
- name: `?accHitTest@COutlineView32@@UEAAJJJPEAUtagVARIANT@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(COutlineView32 *__hidden this, int, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x1800191c0`
- `0x18003b854`
- `0x18003bd70`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003beb4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003beb4`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003be25`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003be58`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003be25`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x18003be58`
- `USER32!ScreenToClient` at `0x18003be3b`
- `USER32!ScreenToClient` at `0x18003be3b`

## pseudocode

```c
unsigned int __fastcall COutlineView32::accHitTest(HWND *this, int a2, int a3, struct tagVARIANT *a4)
{
  HWND v4; // rax
  unsigned int result; // eax
  char *v10; // rax
  __int64 v11; // rdi
  HWND v12; // rcx
  int v13; // r15d
  LONG v14; // eax
  struct tagPOINT Point; // [rsp+40h] [rbp-20h] BYREF
  struct _TREEITEM *v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 Buffer; // [rsp+50h] [rbp-10h] BYREF
  HANDLE hProcess; // [rsp+90h] [rbp+30h] BYREF

  v4 = *this;
  hProcess = 0;
  Point = 0;
  (*((void (__fastcall **)(HWND *))v4 + 29))(this);
  result = CClient::accHitTest((CClient *)this, a2, a3, a4);
  if ( !result && a4->vt == 3 && !a4->lVal )
  {
    v10 = (char *)SharedAlloc(0x18u, this[10], &hProcess);
    v11 = (__int64)v10;
    if ( v10 )
    {
      Buffer = 0;
      WriteProcessMemory(hProcess, v10 + 16, &Buffer, 8u, 0);
      v12 = this[10];
      Point.x = a2;
      Point.y = a3;
      ScreenToClient(v12, &Point);
      WriteProcessMemory(hProcess, (LPVOID)v11, &Point, 8u, 0);
      v13 = CAccessible::AccSendMessageTimeout((CAccessible *)this, 0, this[10], 0x1111u, 0, v11, 0);
      if ( v13 >= 0 )
      {
        v16 = 0;
        ReadProcessMemory(hProcess, (LPCVOID)(v11 + 16), &v16, 8u, 0);
        SharedFree((void *)v11, hProcess);
        if ( v16 )
        {
          v14 = ChildIDFromTVItem(this[10], v16);
          a4->lVal = v14;
          return v14 == 0 ? 0x80004005 : 0;
        }
        else
        {
          a4->lVal = 0;
          return 0;
        }
      }
      else
      {
        SharedFree((void *)v11, hProcess);
        return v13;
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
0x18003bd70  mov     [rsp-28h+arg_8], rbx
0x18003bd75  mov     [rsp-28h+arg_10], rsi
0x18003bd7a  push    rbp
0x18003bd7b  push    rdi
0x18003bd7c  push    r12
0x18003bd7e  push    r13
0x18003bd80  push    r15
0x18003bd82  mov     rbp, rsp
0x18003bd85  sub     rsp, 60h
0x18003bd89  mov     rax, [rcx]
0x18003bd8c  mov     rbx, r9
0x18003bd8f  mov     r15d, r8d
0x18003bd92  mov     [rbp+hProcess], 0
0x18003bd9a  mov     r13d, edx
0x18003bd9d  mov     qword ptr [rbp+Point.x], 0
0x18003bda5  mov     rsi, rcx
0x18003bda8  mov     rax, [rax+0E8h]
0x18003bdaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdb4  mov     r9, rbx; struct tagVARIANT *
0x18003bdb7  mov     r8d, r15d; int
0x18003bdba  mov     edx, r13d; int
0x18003bdbd  mov     rcx, rsi; this
0x18003bdc0  call    ?accHitTest@CClient@@UEAAJJJPEAUtagVARIANT@@@Z; CClient::accHitTest(long,long,tagVARIANT *)
0x18003bdc5  test    eax, eax
0x18003bdc7  jnz     loc_18003BEEE
0x18003bdcd  cmp     word ptr [rbx], 3
0x18003bdd1  jnz     loc_18003BEEE
0x18003bdd7  cmp     [rbx+8], eax
0x18003bdda  jnz     loc_18003BEEE
0x18003bde0  mov     rdx, [rsi+50h]; HWND
0x18003bde4  lea     r8, [rbp+hProcess]; void **
0x18003bde8  lea     ecx, [rax+18h]; dwSize
0x18003bdeb  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x18003bdf0  mov     rdi, rax
0x18003bdf3  test    rax, rax
0x18003bdf6  jnz     short loc_18003BE02
0x18003bdf8  mov     eax, 8007000Eh
0x18003bdfd  jmp     loc_18003BEEE
0x18003be02  mov     rcx, [rbp+hProcess]; hProcess
0x18003be06  lea     r8, [rbp+Buffer]; lpBuffer
0x18003be0a  mov     r9d, 8; nSize
0x18003be10  mov     [rbp+Buffer], 0
0x18003be18  lea     rdx, [rax+10h]; lpBaseAddress
0x18003be1c  mov     [rsp+60h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x18003be25  call    cs:__imp_WriteProcessMemory
0x18003be2b  mov     rcx, [rsi+50h]; hWnd
0x18003be2f  lea     rdx, [rbp+Point]; lpPoint
0x18003be33  mov     [rbp+Point.x], r13d
0x18003be37  mov     [rbp+Point.y], r15d
0x18003be3b  call    cs:__imp_ScreenToClient
0x18003be41  mov     rcx, [rbp+hProcess]; hProcess
0x18003be45  lea     r8, [rbp+Point]; lpBuffer
0x18003be49  xor     r13d, r13d
0x18003be4c  mov     rdx, rdi; lpBaseAddress
0x18003be4f  mov     [rsp+60h+lpNumberOfBytesWritten], r13; lpNumberOfBytesWritten
0x18003be54  lea     r9d, [r13+8]; nSize
0x18003be58  call    cs:__imp_WriteProcessMemory
0x18003be5e  mov     r8, [rsi+50h]; HWND
0x18003be62  mov     r9d, 1111h; unsigned int
0x18003be68  mov     [rsp+60h+var_30], r13; __int64 *
0x18003be6d  xor     edx, edx; bool
0x18003be6f  mov     [rsp+60h+var_38], rdi; __int64
0x18003be74  mov     rcx, rsi; this
0x18003be77  mov     [rsp+60h+lpNumberOfBytesWritten], r13; unsigned __int64
0x18003be7c  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18003be81  mov     r15d, eax
0x18003be84  test    eax, eax
0x18003be86  jns     short loc_18003BE99
0x18003be88  mov     rdx, [rbp+hProcess]; hProcess
0x18003be8c  mov     rcx, rdi; lpAddress
0x18003be8f  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003be94  mov     eax, r15d
0x18003be97  jmp     short loc_18003BEEE
0x18003be99  mov     rcx, [rbp+hProcess]; hProcess
0x18003be9d  lea     r8, [rbp+var_18]; lpBuffer
0x18003bea1  mov     r9d, 8; nSize
0x18003bea7  mov     [rbp+var_18], r13
0x18003beab  lea     rdx, [rdi+10h]; lpBaseAddress
0x18003beaf  mov     [rsp+60h+lpNumberOfBytesWritten], r13; lpNumberOfBytesRead
0x18003beb4  call    cs:__imp_ReadProcessMemory
0x18003beba  mov     rdx, [rbp+hProcess]; hProcess
0x18003bebe  mov     rcx, rdi; lpAddress
0x18003bec1  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x18003bec6  mov     rdx, [rbp+var_18]; struct _TREEITEM *
0x18003beca  test    rdx, rdx
0x18003becd  jz      short loc_18003BEE8
0x18003becf  mov     rcx, [rsi+50h]; HWND
0x18003bed3  call    ?ChildIDFromTVItem@@YAKPEAUHWND__@@PEAU_TREEITEM@@@Z; ChildIDFromTVItem(HWND__ *,_TREEITEM *)
0x18003bed8  mov     [rbx+8], eax
0x18003bedb  neg     eax
0x18003bedd  sbb     eax, eax
0x18003bedf  not     eax
0x18003bee1  and     eax, 80004005h
0x18003bee6  jmp     short loc_18003BEEE
0x18003bee8  mov     [rbx+8], r13d
0x18003beec  xor     eax, eax
0x18003beee  lea     r11, [rsp+60h+var_s0]
0x18003bef3  mov     rbx, [r11+38h]
0x18003bef7  mov     rsi, [r11+40h]
0x18003befb  mov     rsp, r11
0x18003befe  pop     r15
0x18003bf00  pop     r13
0x18003bf02  pop     r12
0x18003bf04  pop     rdi
0x18003bf05  pop     rbp
0x18003bf06  retn
```
