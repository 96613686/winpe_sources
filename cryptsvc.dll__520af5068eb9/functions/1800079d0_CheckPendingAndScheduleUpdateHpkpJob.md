# CheckPendingAndScheduleUpdateHpkpJob

- ea: `0x1800079d0`
- end: `0x180007a6f`
- name: `CheckPendingAndScheduleUpdateHpkpJob`
- size: `159`
- prototype: `void()`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180006aa0`
- `0x1800110b4`

## callees

- `0x1800033a0`
- `0x1800068b0`
- `0x1800068f0`
- `0x1800079d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800079de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800079de`

## pseudocode

```c
void CheckPendingAndScheduleUpdateHpkpJob()
{
  ULONGLONG TickCount64; // rax
  FILETIME v1; // rax
  void *v2; // rbx

  if ( !qword_180020400 )
  {
    TickCount64 = GetTickCount64();
    if ( TickCount64 >= qword_1800203F8 + 300000
      && (!qword_1800203F8 || dword_180020410 || TickCount64 > qword_1800203F8 + 172800000)
      && !g_fTestHpkp )
    {
      qword_1800203F8 = TickCount64;
      v1 = (FILETIME)PkiZeroAlloc(0x20u);
      v2 = (void *)v1;
      if ( v1 )
      {
        if ( (unsigned int)AddToBeRunJobEx(v1, 8, 0, 1) )
          qword_180020400 = (__int64)v2;
        else
          PkiFree(v2);
      }
    }
  }
}

```

## disassembly

```asm
0x1800079d0  sub     rsp, 28h
0x1800079d4  cmp     cs:qword_180020400, 0
0x1800079dc  jnz     short loc_180007A11
0x1800079de  call    cs:__imp_GetTickCount64
0x1800079e4  mov     rcx, cs:qword_1800203F8
0x1800079eb  lea     rdx, [rcx+493E0h]
0x1800079f2  cmp     rax, rdx
0x1800079f5  jb      short loc_180007A11
0x1800079f7  test    rcx, rcx
0x1800079fa  jz      short loc_180007A16
0x1800079fc  cmp     cs:dword_180020410, 0
0x180007a03  jnz     short loc_180007A16
0x180007a05  add     rcx, 0A4CB800h
0x180007a0c  cmp     rax, rcx
0x180007a0f  ja      short loc_180007A16
0x180007a11  add     rsp, 28h
0x180007a15  retn
0x180007a16  cmp     cs:g_fTestHpkp, 0
0x180007a1d  jnz     short loc_180007A11
0x180007a1f  mov     ecx, 20h ; ' '; uBytes
0x180007a24  mov     [rsp+28h+var_8], rbx
0x180007a29  mov     cs:qword_1800203F8, rax
0x180007a30  call    PkiZeroAlloc
0x180007a35  mov     rbx, rax
0x180007a38  test    rax, rax
0x180007a3b  jz      short loc_180007A5E
0x180007a3d  mov     r9d, 1
0x180007a43  xor     r8d, r8d
0x180007a46  mov     edx, 8
0x180007a4b  mov     rcx, rax
0x180007a4e  call    AddToBeRunJobEx
0x180007a53  test    eax, eax
0x180007a55  jz      short loc_180007A65
0x180007a57  mov     cs:qword_180020400, rbx
0x180007a5e  mov     rbx, [rsp+28h+var_8]
0x180007a63  jmp     short loc_180007A11
0x180007a65  mov     rcx, rbx; hMem
0x180007a68  call    PkiFree
0x180007a6d  jmp     short loc_180007A5E
```
