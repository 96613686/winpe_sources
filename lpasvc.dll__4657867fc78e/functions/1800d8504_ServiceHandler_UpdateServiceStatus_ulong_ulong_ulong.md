# ServiceHandler::UpdateServiceStatus(ulong,ulong,ulong)

- ea: `0x1800d8504`
- end: `0x1800d854e`
- name: `?UpdateServiceStatus@ServiceHandler@@AEAAXKKK@Z`
- size: `74`
- prototype: `void __fastcall(ServiceHandler *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800d7d70`
- `0x1800d7f14`
- `0x1800d8118`
- `0x1800d8390`

## callees

- `0x1800d8504`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800d8543`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800d8543`

## pseudocode

```c
void __fastcall ServiceHandler::UpdateServiceStatus(ServiceHandler *this, int a2, int a3, int a4)
{
  int v4; // edx
  int v5; // edx

  if ( *((_QWORD *)this + 1) )
  {
    *((_DWORD *)this + 5) = a2;
    *((_DWORD *)this + 6) = 325;
    *((_DWORD *)this + 7) = a3;
    *((_DWORD *)this + 10) = a4;
    v4 = a2 - 1;
    if ( !v4 || v4 == 3 )
    {
      v5 = 0;
    }
    else
    {
      v5 = *((_DWORD *)this + 24);
      *((_DWORD *)this + 24) = v5 + 1;
    }
    *((_DWORD *)this + 9) = v5;
    SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 1), (LPSERVICE_STATUS)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x1800d8504  sub     rsp, 28h
0x1800d8508  cmp     qword ptr [rcx+8], 0
0x1800d850d  jz      short loc_1800D8549
0x1800d850f  mov     [rcx+14h], edx
0x1800d8512  mov     dword ptr [rcx+18h], 145h
0x1800d8519  mov     [rcx+1Ch], r8d
0x1800d851d  mov     [rcx+28h], r9d
0x1800d8521  sub     edx, 1
0x1800d8524  jz      short loc_1800D8536
0x1800d8526  cmp     edx, 3
0x1800d8529  jz      short loc_1800D8536
0x1800d852b  mov     edx, [rcx+60h]
0x1800d852e  lea     eax, [rdx+1]
0x1800d8531  mov     [rcx+60h], eax
0x1800d8534  jmp     short loc_1800D8538
0x1800d8536  xor     edx, edx
0x1800d8538  mov     [rcx+24h], edx
0x1800d853b  lea     rdx, [rcx+10h]; lpServiceStatus
0x1800d853f  mov     rcx, [rcx+8]; hServiceStatus
0x1800d8543  call    cs:__imp_SetServiceStatus
0x1800d8549  add     rsp, 28h
0x1800d854d  retn
```
