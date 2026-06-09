# StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)

- ea: `0x18003ad7c`
- end: `0x18003ae1d`
- name: `??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(StateRepository::Cache::Entity::Package_NoThrow *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x18003db44`
- `0x18003f588`
- `0x18003f8a8`
- `0x180098d14`
- `0x180099440`
- `0x1800a0c70`
- `0x1800b7a8c`
- `0x1800ba1ec`
- `0x1800bb7b0`
- `0x1800bbd60`
- `0x1800c1e6b`
- `0x1800c1f31`
- `0x1800c7a45`

## callees

- `0x18003ad7c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ad96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003adb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003add0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003aded`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ae0a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ad96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003adb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003add0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003aded`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003ae0a`

## pseudocode

```c
void __fastcall StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(
        StateRepository::Cache::Entity::Package_NoThrow *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v2 )
    SRCache_Free();
  v3 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v3 )
    SRCache_Free();
  v4 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v4 )
    SRCache_Free();
  v5 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v5 )
    SRCache_Free();
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
    SRCache_Free();
}

```

## disassembly

```asm
0x18003ad7c  push    rbx
0x18003ad7e  sub     rsp, 20h
0x18003ad82  mov     rbx, rcx
0x18003ad85  mov     rcx, [rcx+58h]
0x18003ad89  mov     qword ptr [rbx+58h], 0
0x18003ad91  test    rcx, rcx
0x18003ad94  jz      short loc_18003ADA2
0x18003ad96  call    cs:__imp_SRCache_Free
0x18003ad9d  nop     dword ptr [rax+rax+00h]
0x18003ada2  mov     rcx, [rbx+48h]
0x18003ada6  mov     qword ptr [rbx+48h], 0
0x18003adae  test    rcx, rcx
0x18003adb1  jz      short loc_18003ADBF
0x18003adb3  call    cs:__imp_SRCache_Free
0x18003adba  nop     dword ptr [rax+rax+00h]
0x18003adbf  mov     rcx, [rbx+40h]
0x18003adc3  mov     qword ptr [rbx+40h], 0
0x18003adcb  test    rcx, rcx
0x18003adce  jz      short loc_18003ADDC
0x18003add0  call    cs:__imp_SRCache_Free
0x18003add7  nop     dword ptr [rax+rax+00h]
0x18003addc  mov     rcx, [rbx+38h]
0x18003ade0  mov     qword ptr [rbx+38h], 0
0x18003ade8  test    rcx, rcx
0x18003adeb  jz      short loc_18003ADF9
0x18003aded  call    cs:__imp_SRCache_Free
0x18003adf4  nop     dword ptr [rax+rax+00h]
0x18003adf9  mov     rcx, [rbx+8]
0x18003adfd  mov     qword ptr [rbx+8], 0
0x18003ae05  test    rcx, rcx
0x18003ae08  jz      short loc_18003AE16
0x18003ae0a  call    cs:__imp_SRCache_Free
0x18003ae11  nop     dword ptr [rax+rax+00h]
0x18003ae16  add     rsp, 20h
0x18003ae1a  pop     rbx
0x18003ae1b  retn
```
