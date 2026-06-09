# NDownLevelCrew::TWorkCrew::Initialize(void)

- ea: `0x14005c87c`
- end: `0x14005c921`
- name: `?Initialize@TWorkCrew@NDownLevelCrew@@AEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14005c088`

## callees

- `0x140005358`
- `0x14005c87c`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x14005c904`
- `KERNEL32!RegisterWaitForSingleObject` at `0x14005c904`
- `KERNEL32!CreateEventW` at `0x14005c89c`
- `KERNEL32!CreateEventW` at `0x14005c8c1`
- `KERNEL32!CreateEventW` at `0x14005c89c`
- `KERNEL32!CreateEventW` at `0x14005c8c1`

## pseudocode

```c
__int64 __fastcall NDownLevelCrew::TWorkCrew::Initialize(unsigned int *Context)
{
  __int64 result; // rax
  HANDLE EventW; // rax
  NCoreLibrary *v4; // rcx
  HANDLE v5; // rax
  NCoreLibrary *v6; // rcx
  NCoreLibrary *v7; // rcx

  result = Context[20];
  if ( (int)result >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)Context + 22) = EventW;
    if ( EventW || (result = NCoreLibrary::GetLastErrorAsHResult(v4), (int)result >= 0) )
    {
      v5 = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)Context + 23) = v5;
      if ( v5 || (result = NCoreLibrary::GetLastErrorAsHResult(v6), (int)result >= 0) )
      {
        if ( RegisterWaitForSingleObject(
               (PHANDLE)Context + 24,
               *((HANDLE *)Context + 23),
               NDownLevelCrew::TWorkCrew::CancelWork,
               Context,
               0xFFFFFFFF,
               0x10u) )
        {
          return 0;
        }
        else
        {
          return NCoreLibrary::GetLastErrorAsHResult(v7);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14005c87c  push    rbx
0x14005c87e  sub     rsp, 30h
0x14005c882  mov     eax, [rcx+50h]
0x14005c885  mov     rbx, rcx
0x14005c888  test    eax, eax
0x14005c88a  js      loc_14005C91B
0x14005c890  xor     r9d, r9d; lpName
0x14005c893  xor     r8d, r8d; bInitialState
0x14005c896  xor     ecx, ecx; lpEventAttributes
0x14005c898  lea     edx, [r9+1]; bManualReset
0x14005c89c  call    cs:__imp_CreateEventW
0x14005c8a2  mov     [rbx+0B0h], rax
0x14005c8a9  test    rax, rax
0x14005c8ac  jnz     short loc_14005C8B7
0x14005c8ae  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14005c8b3  test    eax, eax
0x14005c8b5  js      short loc_14005C91B
0x14005c8b7  xor     r9d, r9d; lpName
0x14005c8ba  xor     r8d, r8d; bInitialState
0x14005c8bd  xor     edx, edx; bManualReset
0x14005c8bf  xor     ecx, ecx; lpEventAttributes
0x14005c8c1  call    cs:__imp_CreateEventW
0x14005c8c7  mov     [rbx+0B8h], rax
0x14005c8ce  test    rax, rax
0x14005c8d1  jnz     short loc_14005C8DC
0x14005c8d3  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14005c8d8  test    eax, eax
0x14005c8da  js      short loc_14005C91B
0x14005c8dc  mov     rdx, [rbx+0B8h]; hObject
0x14005c8e3  lea     rcx, [rbx+0C0h]; phNewWaitObject
0x14005c8ea  mov     [rsp+38h+dwFlags], 10h; dwFlags
0x14005c8f2  lea     r8, ?CancelWork@TWorkCrew@NDownLevelCrew@@CAXPEAXE@Z; Callback
0x14005c8f9  mov     r9, rbx; Context
0x14005c8fc  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x14005c904  call    cs:__imp_RegisterWaitForSingleObject
0x14005c90a  test    eax, eax
0x14005c90c  jz      short loc_14005C916
0x14005c90e  xor     eax, eax
0x14005c910  add     rsp, 30h
0x14005c914  pop     rbx
0x14005c915  retn
0x14005c916  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14005c91b  add     rsp, 30h
0x14005c91f  pop     rbx
0x14005c920  retn
```
