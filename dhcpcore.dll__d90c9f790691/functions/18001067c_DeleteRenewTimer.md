# DeleteRenewTimer

- ea: `0x18001067c`
- end: `0x1800106e2`
- name: `DeleteRenewTimer`
- size: `102`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180023928`

## callees

- `0x18001067c`
- `0x18004d9e8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800106b6`
- `ntdll!RtlNtStatusToDosError` at `0x1800106b6`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x18001069a`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x18001069a`

## pseudocode

```c
__int64 __fastcall DeleteRenewTimer(__int64 *a1)
{
  ULONG v1; // edi
  __int64 v3; // rcx
  NTSTATUS v4; // eax
  ULONG v6; // eax

  v1 = 0;
  if ( a1 )
  {
    v3 = *a1;
    if ( v3 )
    {
      v4 = EaDeleteAggregatedEvent(v3, 0);
      if ( v4 < 0 )
      {
        v6 = RtlNtStatusToDosError(v4);
        v1 = v6;
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_d(1025, 65, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, v6);
      }
      else
      {
        *a1 = 0;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001067c  mov     [rsp+arg_0], rbx
0x180010681  push    rdi
0x180010682  sub     rsp, 20h
0x180010686  xor     edi, edi
0x180010688  mov     rbx, rcx
0x18001068b  test    rcx, rcx
0x18001068e  jz      short loc_1800106A7
0x180010690  mov     rcx, [rcx]
0x180010693  test    rcx, rcx
0x180010696  jz      short loc_1800106A7
0x180010698  xor     edx, edx
0x18001069a  call    cs:__imp_EaDeleteAggregatedEvent
0x1800106a0  test    eax, eax
0x1800106a2  js      short loc_1800106B4
0x1800106a4  mov     [rbx], rdi
0x1800106a7  mov     rbx, [rsp+28h+arg_0]
0x1800106ac  mov     eax, edi
0x1800106ae  add     rsp, 20h
0x1800106b2  pop     rdi
0x1800106b3  retn
0x1800106b4  mov     ecx, eax; Status
0x1800106b6  call    cs:__imp_RtlNtStatusToDosError
0x1800106bc  mov     edi, eax
0x1800106be  test    byte ptr cs:xmmword_1800616A0, 2
0x1800106c5  jz      short loc_1800106A7
0x1800106c7  mov     edx, 41h ; 'A'
0x1800106cc  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x1800106d3  mov     ecx, 401h
0x1800106d8  mov     r9d, eax
0x1800106db  call    WPP_SF_d
0x1800106e0  jmp     short loc_1800106A7
```
