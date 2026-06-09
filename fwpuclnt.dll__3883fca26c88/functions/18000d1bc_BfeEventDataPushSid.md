# BfeEventDataPushSid

- ea: `0x18000d1bc`
- end: `0x18000d227`
- name: `BfeEventDataPushSid`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005c4c`

## callees

- `0x18000d1bc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000d1cf`
- `ntdll!RtlLengthSid` at `0x18000d1cf`

## pseudocode

```c
int __fastcall BfeEventDataPushSid(_DWORD *a1, void *a2)
{
  __int64 *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // edx

  LODWORD(v4) = RtlLengthSid(a2);
  if ( (_DWORD)v4 )
  {
    v5 = 2LL * (unsigned int)*a1;
    *(_QWORD *)&a1[2 * v5 + 2] = a2;
    a1[2 * v5 + 4] = (_DWORD)v4;
    a1[2 * v5 + 5] = 0;
    ++*a1;
    v6 = (((_DWORD)v4 + 7) & 0xFFFFFFF8) - (_DWORD)v4;
    if ( v6 )
    {
      v4 = &qword_18007C4B0;
      a1[2 * v5 + 8] = v6;
      *(_QWORD *)&a1[2 * v5 + 6] = &qword_18007C4B0;
      a1[2 * v5 + 9] = 0;
      ++*a1;
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18000d1bc  mov     [rsp+arg_0], rbx
0x18000d1c1  push    rdi
0x18000d1c2  sub     rsp, 20h
0x18000d1c6  mov     rbx, rcx
0x18000d1c9  mov     rdi, rdx
0x18000d1cc  mov     rcx, rdx; Sid
0x18000d1cf  call    cs:__imp_RtlLengthSid
0x18000d1d6  nop     dword ptr [rax+rax+00h]
0x18000d1db  test    eax, eax
0x18000d1dd  jz      short loc_18000D21B
0x18000d1df  mov     ecx, [rbx]
0x18000d1e1  lea     edx, [rax+7]
0x18000d1e4  add     rcx, rcx
0x18000d1e7  and     edx, 0FFFFFFF8h
0x18000d1ea  mov     [rbx+rcx*8+8], rdi
0x18000d1ef  mov     [rbx+rcx*8+10h], eax
0x18000d1f3  mov     dword ptr [rbx+rcx*8+14h], 0
0x18000d1fb  inc     dword ptr [rbx]
0x18000d1fd  sub     edx, eax
0x18000d1ff  jz      short loc_18000D21B
0x18000d201  lea     rax, qword_18007C4B0
0x18000d208  mov     [rbx+rcx*8+20h], edx
0x18000d20c  mov     [rbx+rcx*8+18h], rax
0x18000d211  mov     dword ptr [rbx+rcx*8+24h], 0
0x18000d219  inc     dword ptr [rbx]
0x18000d21b  mov     rbx, [rsp+28h+arg_0]
0x18000d220  add     rsp, 20h
0x18000d224  pop     rdi
0x18000d225  retn
```
