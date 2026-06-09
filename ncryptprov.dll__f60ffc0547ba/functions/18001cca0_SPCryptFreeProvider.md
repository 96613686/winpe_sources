# SPCryptFreeProvider

- ea: `0x18001cca0`
- end: `0x18001cdb5`
- name: `SPCryptFreeProvider`
- size: `277`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b250`
- `0x18000d3d0`
- `0x18001cca0`
- `0x180038970`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18001cd20`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001cd20`
- `ntdll!RtlReleaseResource` at `0x18001cd41`
- `ntdll!RtlReleaseResource` at `0x18001cd41`
- `ntdll!RtlDeleteResource` at `0x18001cd50`
- `ntdll!RtlDeleteResource` at `0x18001cd50`
- `ntdll!RtlFreeHeap` at `0x18001cd7b`
- `ntdll!RtlFreeHeap` at `0x18001cd7b`

## string_xrefs

- `0x18001cced`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall SPCryptFreeProvider(char *a1, int a2, int a3)
{
  unsigned int v4; // ebx
  struct _RTL_RESOURCE *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx

  if ( a1 && *(_DWORD *)a1 >= 0xA0u && *((_DWORD *)a1 + 1) == 1263751248 )
  {
    v5 = (struct _RTL_RESOURCE *)(a1 + 64);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(a1 + 64), 1u);
    v6 = *((_QWORD *)a1 + 4);
    if ( v6 )
    {
      MSCryptFree(v6);
      *((_QWORD *)a1 + 4) = 0;
    }
    v7 = *((_QWORD *)a1 + 5);
    if ( v7 )
    {
      MSCryptFree(v7);
      *((_QWORD *)a1 + 5) = 0;
    }
    RtlReleaseResource(v5);
    RtlDeleteResource(v5);
    memset_0(a1, 0, *(unsigned int *)a1);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
    return 0;
  }
  else
  {
    v4 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        32);
  }
  return v4;
}

```

## disassembly

```asm
0x18001cca0  mov     [rsp+arg_0], rbx
0x18001cca5  push    rdi
0x18001cca6  sub     rsp, 40h
0x18001ccaa  mov     rbx, rcx
0x18001ccad  test    rcx, rcx
0x18001ccb0  jz      short loc_18001CCC3
0x18001ccb2  cmp     dword ptr [rcx], 0A0h
0x18001ccb8  jb      short loc_18001CCC3
0x18001ccba  cmp     dword ptr [rcx+4], 4B535050h
0x18001ccc1  jz      short loc_18001CD17
0x18001ccc3  mov     ebx, 80090026h
0x18001ccc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cccf  lea     rax, WPP_GLOBAL_Control
0x18001ccd6  cmp     rcx, rax
0x18001ccd9  jz      loc_18001CD89
0x18001ccdf  test    byte ptr [rcx+1Ch], 1
0x18001cce3  jz      loc_18001CD89
0x18001cce9  mov     rcx, [rcx+10h]
0x18001cced  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ccf4  mov     [rsp+48h+var_18], 0D20h
0x18001ccfc  lea     r9, aStatus; "Status"
0x18001cd03  mov     [rsp+48h+var_20], rax
0x18001cd08  mov     [rsp+48h+var_28], 80090026h
0x18001cd10  call    WPP_SF_sDsd
0x18001cd15  jmp     short loc_18001CD89
0x18001cd17  lea     rdi, [rcx+40h]
0x18001cd1b  mov     dl, 1; Wait
0x18001cd1d  mov     rcx, rdi; Resource
0x18001cd20  call    cs:__imp_RtlAcquireResourceExclusive
0x18001cd27  nop     dword ptr [rax+rax+00h]
0x18001cd2c  mov     rcx, [rbx+20h]
0x18001cd30  test    rcx, rcx
0x18001cd33  jnz     short loc_18001CDA6
0x18001cd35  mov     rcx, [rbx+28h]
0x18001cd39  test    rcx, rcx
0x18001cd3c  jnz     short loc_18001CD97
0x18001cd3e  mov     rcx, rdi; Resource
0x18001cd41  call    cs:__imp_RtlReleaseResource
0x18001cd48  nop     dword ptr [rax+rax+00h]
0x18001cd4d  mov     rcx, rdi; Resource
0x18001cd50  call    cs:__imp_RtlDeleteResource
0x18001cd57  nop     dword ptr [rax+rax+00h]
0x18001cd5c  mov     r8d, [rbx]; Size
0x18001cd5f  xor     edx, edx; Val
0x18001cd61  mov     rcx, rbx; void *
0x18001cd64  call    memset_0
0x18001cd69  mov     rcx, gs:60h
0x18001cd72  mov     r8, rbx; P
0x18001cd75  xor     edx, edx; Flags
0x18001cd77  mov     rcx, [rcx+30h]; HeapHandle
0x18001cd7b  call    cs:__imp_RtlFreeHeap
0x18001cd82  nop     dword ptr [rax+rax+00h]
0x18001cd87  xor     ebx, ebx
0x18001cd89  mov     eax, ebx
0x18001cd8b  mov     rbx, [rsp+48h+arg_0]
0x18001cd90  add     rsp, 40h
0x18001cd94  pop     rdi
0x18001cd95  retn
0x18001cd97  call    MSCryptFree
0x18001cd9c  mov     qword ptr [rbx+28h], 0
0x18001cda4  jmp     short loc_18001CD3E
0x18001cda6  call    MSCryptFree
0x18001cdab  mov     qword ptr [rbx+20h], 0
0x18001cdb3  jmp     short loc_18001CD35
```
