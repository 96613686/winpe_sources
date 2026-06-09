# LanSvcUpdateStatus(void)

- ea: `0x18000c02c`
- end: `0x18000c089`
- name: `?LanSvcUpdateStatus@@YAKXZ`
- size: `93`
- prototype: `DWORD __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x18000aac0`
- `0x18000b5e0`
- `0x18000b814`

## callees

- `0x18000c02c`
- `0x18000c2ac`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c06d`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c06d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c082`

## pseudocode

```c
DWORD __fastcall LanSvcUpdateStatus(__int64 a1, __int64 a2, __int64 a3)
{
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_l(WPP_GLOBAL_Control[1].Flink, a2, a3, g_LanServiceStatus.dwCurrentState);
  }
  if ( SetServiceStatus(g_hLanServiceStatusHandle, &g_LanServiceStatus) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18000c02c  sub     rsp, 28h
0x18000c030  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c037  lea     rax, WPP_GLOBAL_Control
0x18000c03e  cmp     rcx, rax
0x18000c041  jz      short loc_18000C05F
0x18000c043  cmp     byte ptr [rcx+19h], 4
0x18000c047  jb      short loc_18000C05F
0x18000c049  test    byte ptr [rcx+1Ch], 1
0x18000c04d  jz      short loc_18000C05F
0x18000c04f  mov     r9d, cs:?g_LanServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS g_LanServiceStatus ...
0x18000c056  mov     rcx, [rcx+10h]
0x18000c05a  call    WPP_SF_l
0x18000c05f  mov     rcx, cs:?g_hLanServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000c066  lea     rdx, ?g_LanServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000c06d  call    cs:__imp_SetServiceStatus
0x18000c073  test    eax, eax
0x18000c075  jz      short loc_18000C07E
0x18000c077  xor     eax, eax
0x18000c079  add     rsp, 28h
0x18000c07d  retn
0x18000c07e  add     rsp, 28h
0x18000c082  jmp     cs:__imp_GetLastError
```
