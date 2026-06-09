# IsHwndInProcess(HWND__ *)

- ea: `0x180001520`
- end: `0x180001566`
- name: `?IsHwndInProcess@@YA_NPEAUHWND__@@@Z`
- size: `70`
- prototype: `bool __fastcall(HWND hWnd)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180001060`
- `0x180001570`
- `0x18000a3c0`
- `0x180013ca0`
- `0x180013ed0`
- `0x180014190`

## callees

- `0x180001520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000152d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000152d`
- `USER32!GetWindowThreadProcessId` at `0x180001545`
- `USER32!GetWindowThreadProcessId` at `0x180001545`

## pseudocode

```c
bool __fastcall IsHwndInProcess(HWND hWnd)
{
  DWORD CurrentProcessId; // eax
  DWORD v3; // edi
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  dwProcessId = 0;
  v3 = CurrentProcessId;
  return GetWindowThreadProcessId(hWnd, &dwProcessId) && dwProcessId == v3;
}

```

## disassembly

```asm
0x180001520  mov     [rsp+arg_0], rbx
0x180001525  push    rdi
0x180001526  sub     rsp, 20h
0x18000152a  mov     rbx, rcx
0x18000152d  call    cs:__imp_GetCurrentProcessId
0x180001533  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180001538  mov     [rsp+28h+dwProcessId], 0
0x180001540  mov     rcx, rbx; hWnd
0x180001543  mov     edi, eax
0x180001545  call    cs:__imp_GetWindowThreadProcessId
0x18000154b  test    eax, eax
0x18000154d  jz      short loc_180001562
0x18000154f  cmp     [rsp+28h+dwProcessId], edi
0x180001553  jnz     short loc_180001562
0x180001555  mov     al, 1
0x180001557  mov     rbx, [rsp+28h+arg_0]
0x18000155c  add     rsp, 20h
0x180001560  pop     rdi
0x180001561  retn
0x180001562  xor     al, al
0x180001564  jmp     short loc_180001557
```
